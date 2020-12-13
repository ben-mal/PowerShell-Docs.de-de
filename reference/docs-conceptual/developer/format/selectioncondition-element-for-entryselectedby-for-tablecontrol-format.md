---
ms.date: 09/13/2016
ms.topic: reference
title: Element „SelectionCondition“ für EntrySelectedBy für TableControl (Format)
description: Element „SelectionCondition“ für EntrySelectedBy für TableControl (Format)
ms.openlocfilehash: 22f304615c6433ffb67f3b4046b645d0c37be8a4
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92645766"
---
# <a name="selectioncondition-element-for-entryselectedby-for-tablecontrol-format"></a><span data-ttu-id="c7459-103">Element „SelectionCondition“ für EntrySelectedBy für TableControl (Format)</span><span class="sxs-lookup"><span data-stu-id="c7459-103">SelectionCondition Element for EntrySelectedBy for TableControl (Format)</span></span>

<span data-ttu-id="c7459-104">Definiert die Bedingung, die für die Verwendung in dieser Definition der Tabellenansicht vorhanden sein muss.</span><span class="sxs-lookup"><span data-stu-id="c7459-104">Defines the condition that must exist to use for this definition of the table view.</span></span> <span data-ttu-id="c7459-105">Es gibt keine Beschränkung für die Anzahl der Auswahl Bedingungen, die für eine Tabellendefinition angegeben werden können.</span><span class="sxs-lookup"><span data-stu-id="c7459-105">There is no limit to the number of selection conditions that can be specified for a table definition.</span></span>

<span data-ttu-id="c7459-106">Configuration-Element (Format) viewdefinitions-Element (Format) View-Element (Format) tablecontrol-Element (Format) tablerowentries-Element (Format) tablerowentry-Element (Format) entryselectedby-Element für tablerowentry (Format) selectioncondition-Element für entryselectedby für tablerowentry (Format)</span><span class="sxs-lookup"><span data-stu-id="c7459-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) TableControl Element (Format) TableRowEntries Element (Format) TableRowEntry Element (Format) EntrySelectedBy Element for TableRowEntry (Format) SelectionCondition Element for EntrySelectedBy for TableRowEntry (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="c7459-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="c7459-107">Syntax</span></span>

```xml
<SelectionCondition>
  <TypeName>Nameof.NetType</TypeName>
  <SelectionSetName>NameofSelectionSet</SelectionSetName>
  <PropertyName>.NetTypeProperty</PropertyName>
  <ScriptBlock>ScriptToEvaluate</ScriptBlock>
</SelectionCondition>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="c7459-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="c7459-108">Attributes and Elements</span></span>

<span data-ttu-id="c7459-109">In den folgenden Abschnitten werden Attribute, untergeordnete Elemente und das übergeordnete Element des selectioncondition-Elements beschrieben.</span><span class="sxs-lookup"><span data-stu-id="c7459-109">The following sections describe attributes, child elements, and the parent element of the SelectionCondition element.</span></span>

### <a name="attributes"></a><span data-ttu-id="c7459-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="c7459-110">Attributes</span></span>

<span data-ttu-id="c7459-111">Keine</span><span class="sxs-lookup"><span data-stu-id="c7459-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="c7459-112">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="c7459-112">Child Elements</span></span>

|<span data-ttu-id="c7459-113">Element</span><span class="sxs-lookup"><span data-stu-id="c7459-113">Element</span></span>|<span data-ttu-id="c7459-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c7459-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="c7459-115">Element „PropertyName“ für SelectionCondition für EntrySelectedBy für TableRowEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="c7459-115">PropertyName Element for SelectionCondition for EntrySelectedBy for TableRowEntry (Format)</span></span>](./propertyname-element-for-selectioncondition-for-entryselectedby-for-tablerowentry-format.md)|<span data-ttu-id="c7459-116">Optionales Element.</span><span class="sxs-lookup"><span data-stu-id="c7459-116">Optional element.</span></span><br /><br /> <span data-ttu-id="c7459-117">Gibt die .net-Eigenschaft an, die die Bedingung auslöst.</span><span class="sxs-lookup"><span data-stu-id="c7459-117">Specifies the .NET property that triggers the condition.</span></span>|
|[<span data-ttu-id="c7459-118">ScriptBlock-Element für selectioncondition für entryselectedby für tablerowentry (Format)</span><span class="sxs-lookup"><span data-stu-id="c7459-118">ScriptBlock Element for SelectionCondition for EntrySelectedBy for TableRowEntry (Format)</span></span>](./scriptblock-element-for-selectioncondition-for-entryselectedby-for-tablecontrol-format.md)|<span data-ttu-id="c7459-119">Optionales Element.</span><span class="sxs-lookup"><span data-stu-id="c7459-119">Optional element.</span></span><br /><br /> <span data-ttu-id="c7459-120">Gibt das Skript an, das die Bedingung auslöst.</span><span class="sxs-lookup"><span data-stu-id="c7459-120">Specifies the script that triggers the condition.</span></span>|
|[<span data-ttu-id="c7459-121">Selectionsetname-Element für selectioncondition für entryselectedby für tablerowentry (Format)</span><span class="sxs-lookup"><span data-stu-id="c7459-121">SelectionSetName Element for SelectionCondition for EntrySelectedBy for TableRowEntry (Format)</span></span>](./selectionsetname-element-for-selectioncondition-for-entryselectedby-for-tablecontrol-format.md)|<span data-ttu-id="c7459-122">Optionales Element.</span><span class="sxs-lookup"><span data-stu-id="c7459-122">Optional element.</span></span><br /><br /> <span data-ttu-id="c7459-123">Gibt den Satz von .NET-Typen an, die die Bedingung auslöst.</span><span class="sxs-lookup"><span data-stu-id="c7459-123">Specifies the set of .NET types that trigger the condition.</span></span>|
|[<span data-ttu-id="c7459-124">Typname-Element für selectioncondition für entryselectedby für tablerowentry (Format)</span><span class="sxs-lookup"><span data-stu-id="c7459-124">TypeName Element for SelectionCondition for EntrySelectedBy for TableRowEntry (Format)</span></span>](./typename-element-for-selectioncondition-for-entryselectedby-for-tablecontrol-format.md)|<span data-ttu-id="c7459-125">Optionales Element.</span><span class="sxs-lookup"><span data-stu-id="c7459-125">Optional element.</span></span><br /><br /> <span data-ttu-id="c7459-126">Gibt einen .NET-Typ an, der die Bedingung auslöst.</span><span class="sxs-lookup"><span data-stu-id="c7459-126">Specifies a .NET type that triggers the condition.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="c7459-127">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="c7459-127">Parent Elements</span></span>

|<span data-ttu-id="c7459-128">Element</span><span class="sxs-lookup"><span data-stu-id="c7459-128">Element</span></span>|<span data-ttu-id="c7459-129">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c7459-129">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="c7459-130">Entryselectedby-Element für tablerowentry (Format)</span><span class="sxs-lookup"><span data-stu-id="c7459-130">EntrySelectedBy Element for TableRowEntry (Format)</span></span>](./entryselectedby-element-for-tablerowentry-for-tablecontrol-format.md)|<span data-ttu-id="c7459-131">Definiert die .NET-Typen, die diesen Tabelleneintrag verwenden, oder die Bedingung, die für die Verwendung dieses Eintrags vorhanden sein muss.</span><span class="sxs-lookup"><span data-stu-id="c7459-131">Defines the .NET types that use this table entry or the condition that must exist for this entry to be used.</span></span>|

## <a name="remarks"></a><span data-ttu-id="c7459-132">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="c7459-132">Remarks</span></span>

<span data-ttu-id="c7459-133">Für jeden Listeneintrag muss mindestens ein Typname, ein Auswahl Satz oder eine Auswahlbedingung definiert sein.</span><span class="sxs-lookup"><span data-stu-id="c7459-133">Each list entry must have at least one type name, selection set, or selection condition defined.</span></span>

<span data-ttu-id="c7459-134">Wenn Sie eine Auswahlbedingung definieren, gelten die folgenden Anforderungen:</span><span class="sxs-lookup"><span data-stu-id="c7459-134">When you are defining a selection condition, the following requirements apply:</span></span>

- <span data-ttu-id="c7459-135">Die Auswahlbedingung muss mindestens einen Eigenschaften Namen oder einen Skriptblock angeben, kann jedoch nicht beides angeben.</span><span class="sxs-lookup"><span data-stu-id="c7459-135">The selection condition must specify a least one property name or a script block, but cannot specify both.</span></span>

- <span data-ttu-id="c7459-136">Die Auswahlbedingung kann eine beliebige Anzahl von .NET-Typen oder-Auswahl Sätzen angeben, kann jedoch nicht beides angeben.</span><span class="sxs-lookup"><span data-stu-id="c7459-136">The selection condition can specify any number of .NET types or selection sets, but cannot specify both.</span></span>

<span data-ttu-id="c7459-137">Weitere Informationen zum Verwenden von Auswahl Bedingungen finden Sie unter Definieren von Bedingungen für den Fall, [dass ein Ansichts Eintrag oder Element verwendet wird](./defining-conditions-for-displaying-data.md).</span><span class="sxs-lookup"><span data-stu-id="c7459-137">For more information about how to use selection conditions, see [Defining Conditions for when a View Entry or Item is Used](./defining-conditions-for-displaying-data.md).</span></span>

<span data-ttu-id="c7459-138">Weitere Informationen zu den Komponenten einer Tabellenansicht finden Sie unter [Erstellen einer Tabellen Sicht](./creating-a-table-view.md).</span><span class="sxs-lookup"><span data-stu-id="c7459-138">For more information about the components of a table view, see [Creating a Table View](./creating-a-table-view.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="c7459-139">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="c7459-139">See Also</span></span>

[<span data-ttu-id="c7459-140">Erstellen einer Tabellenansicht</span><span class="sxs-lookup"><span data-stu-id="c7459-140">Creating a Table View</span></span>](./creating-a-table-view.md)

[<span data-ttu-id="c7459-141">Definieren von Bedingungen für die Anzeige von Daten</span><span class="sxs-lookup"><span data-stu-id="c7459-141">Defining Conditions for When Data Is Displayed</span></span>](./defining-conditions-for-displaying-data.md)

[<span data-ttu-id="c7459-142">Entryselectedby-Element (Format)</span><span class="sxs-lookup"><span data-stu-id="c7459-142">EntrySelectedBy Element (Format)</span></span>](./entryselectedby-element-for-tablerowentry-for-tablecontrol-format.md)

[<span data-ttu-id="c7459-143">Element „PropertyName“ für SelectionCondition für EntrySelectedBy für TableRowEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="c7459-143">PropertyName Element for SelectionCondition for EntrySelectedBy for TableRowEntry (Format)</span></span>](./propertyname-element-for-selectioncondition-for-entryselectedby-for-tablerowentry-format.md)

[<span data-ttu-id="c7459-144">ScriptBlock-Element für selectioncondition für entryselectedby für tablerowentry (Format)</span><span class="sxs-lookup"><span data-stu-id="c7459-144">ScriptBlock Element for SelectionCondition for EntrySelectedBy for TableRowEntry (Format)</span></span>](./scriptblock-element-for-selectioncondition-for-entryselectedby-for-tablecontrol-format.md)

[<span data-ttu-id="c7459-145">Selectionsetname-Element für selectioncondition für entryselectedby für tablerowentry (Format)</span><span class="sxs-lookup"><span data-stu-id="c7459-145">SelectionSetName Element for SelectionCondition for EntrySelectedBy for TableRowEntry (Format)</span></span>](./selectionsetname-element-for-selectioncondition-for-entryselectedby-for-tablecontrol-format.md)

[<span data-ttu-id="c7459-146">Typname-Element für selectioncondition für entryselectedby für tablerowentry (Format)</span><span class="sxs-lookup"><span data-stu-id="c7459-146">TypeName Element for SelectionCondition for EntrySelectedBy for TableRowEntry (Format)</span></span>](./typename-element-for-selectioncondition-for-entryselectedby-for-tablecontrol-format.md)

[<span data-ttu-id="c7459-147">Schreiben einer Windows PowerShell-Formatierungs-und-Typen Datei</span><span class="sxs-lookup"><span data-stu-id="c7459-147">Writing a Windows PowerShell Formatting and Types File</span></span>](./writing-a-powershell-formatting-file.md)
