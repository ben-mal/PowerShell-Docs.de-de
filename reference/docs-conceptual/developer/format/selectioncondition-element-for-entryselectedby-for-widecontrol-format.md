---
ms.date: 09/13/2016
ms.topic: reference
title: Element „SelectionCondition“ für EntrySelectedBy für WideControl (Format)
description: Element „SelectionCondition“ für EntrySelectedBy für WideControl (Format)
ms.openlocfilehash: 8c51ca72edc6ad174dc289c61a8987e8f9495d19
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92655113"
---
# <a name="selectioncondition-element-for-entryselectedby-for-widecontrol-format"></a><span data-ttu-id="aa3d6-103">Element „SelectionCondition“ für EntrySelectedBy für WideControl (Format)</span><span class="sxs-lookup"><span data-stu-id="aa3d6-103">SelectionCondition Element for EntrySelectedBy for WideControl (Format)</span></span>

<span data-ttu-id="aa3d6-104">Definiert die Bedingung, die vorhanden sein muss, damit diese Definition verwendet werden muss.</span><span class="sxs-lookup"><span data-stu-id="aa3d6-104">Defines the condition that must exist for this definition to be used.</span></span> <span data-ttu-id="aa3d6-105">Es gibt keine Beschränkung für die Anzahl der Auswahl Bedingungen, die für eine breite Eingabe Definition angegeben werden können.</span><span class="sxs-lookup"><span data-stu-id="aa3d6-105">There is no limit to the number of selection conditions that can be specified for a wide entry definition.</span></span>

<span data-ttu-id="aa3d6-106">Configuration-Element (Format) viewdefinitions-Element (Format) Ansichts Element (Format) widecontrol-Element (Format) wideentries-Element (Format) wideentry-Element (Format) entryselectedby-Element für wideentry (Format) selectioncondition-Element für entryselectedby für wideentry (Format)</span><span class="sxs-lookup"><span data-stu-id="aa3d6-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) WideControl Element (Format) WideEntries Element (Format) WideEntry Element (Format) EntrySelectedBy Element for WideEntry (Format) SelectionCondition Element for EntrySelectedBy for WideEntry (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="aa3d6-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="aa3d6-107">Syntax</span></span>

```xml
<SelectionCondition>
  <TypeName>Nameof.NetType</TypeName>
  <SelectionSetName>NameofSelectionSet</SelectionSetName>
  <PropertyName>.NetTypeProperty</PropertyName>
  <ScriptBlock>ScriptToEvaluate</ScriptBlock>
</SelectionCondition>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="aa3d6-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="aa3d6-108">Attributes and Elements</span></span>

<span data-ttu-id="aa3d6-109">In den folgenden Abschnitten werden Attribute, untergeordnete Elemente und das übergeordnete Element des- `SelectionCondition` Elements beschrieben.</span><span class="sxs-lookup"><span data-stu-id="aa3d6-109">The following sections describe attributes, child elements, and the parent element of the `SelectionCondition` element.</span></span> <span data-ttu-id="aa3d6-110">Sie müssen ein einzelnes- `PropertyName` oder- `ScriptBlock` Element angeben.</span><span class="sxs-lookup"><span data-stu-id="aa3d6-110">You must specify a single `PropertyName` or `ScriptBlock` element.</span></span> <span data-ttu-id="aa3d6-111">Das `SelectionSetName` -Element und das- `TypeName` Element sind optional.</span><span class="sxs-lookup"><span data-stu-id="aa3d6-111">The `SelectionSetName` and `TypeName` elements are optional.</span></span> <span data-ttu-id="aa3d6-112">Sie können eines der beiden Elemente angeben.</span><span class="sxs-lookup"><span data-stu-id="aa3d6-112">You can specify one of either element.</span></span>

### <a name="attributes"></a><span data-ttu-id="aa3d6-113">Attribute</span><span class="sxs-lookup"><span data-stu-id="aa3d6-113">Attributes</span></span>

<span data-ttu-id="aa3d6-114">Keine</span><span class="sxs-lookup"><span data-stu-id="aa3d6-114">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="aa3d6-115">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="aa3d6-115">Child Elements</span></span>

|<span data-ttu-id="aa3d6-116">Element</span><span class="sxs-lookup"><span data-stu-id="aa3d6-116">Element</span></span>|<span data-ttu-id="aa3d6-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="aa3d6-117">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="aa3d6-118">Element „PropertyName“ für SelectionCondition für EntrySelectedBy für WideEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="aa3d6-118">PropertyName Element for SelectionCondition for EntrySelectedBy for WideEntry (Format)</span></span>](./propertyname-element-for-selectioncondition-for-entryselectedby-for-wideentry-format.md)|<span data-ttu-id="aa3d6-119">Optionales Element.</span><span class="sxs-lookup"><span data-stu-id="aa3d6-119">Optional element.</span></span><br /><br /> <span data-ttu-id="aa3d6-120">Gibt die .net-Eigenschaft an, die die Bedingung auslöst.</span><span class="sxs-lookup"><span data-stu-id="aa3d6-120">Specifies the .NET property that triggers the condition.</span></span>|
|[<span data-ttu-id="aa3d6-121">ScriptBlock-Element für selectioncondition für entryselectedby für wideentry (Format)</span><span class="sxs-lookup"><span data-stu-id="aa3d6-121">ScriptBlock Element for SelectionCondition for EntrySelectedBy for WideEntry (Format)</span></span>](./scriptblock-element-for-selectioncondition-for-entryselectedby-for-widecontrol-format.md)|<span data-ttu-id="aa3d6-122">Optionales Element.</span><span class="sxs-lookup"><span data-stu-id="aa3d6-122">Optional element.</span></span><br /><br /> <span data-ttu-id="aa3d6-123">Gibt den Skriptblock an, der die Bedingung auslöst.</span><span class="sxs-lookup"><span data-stu-id="aa3d6-123">Specifies the script block that triggers the condition.</span></span>|
|[<span data-ttu-id="aa3d6-124">Element „SelectionSetName“ für SelectionCondition für EntrySelectedBy für WideEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="aa3d6-124">SelectionSetName Element for SelectionCondition for EntrySelectedBy for WideEntry (Format)</span></span>](./selectionsetname-element-for-selectioncondition-for-entryselectedby-for-wideentry-format.md)|<span data-ttu-id="aa3d6-125">Optionales Element.</span><span class="sxs-lookup"><span data-stu-id="aa3d6-125">Optional element.</span></span><br /><br /> <span data-ttu-id="aa3d6-126">Gibt den Satz von .NET-Typen an, der die Bedingung auslöst.</span><span class="sxs-lookup"><span data-stu-id="aa3d6-126">Specifies the set of .NET types that triggers the condition.</span></span>|
|[<span data-ttu-id="aa3d6-127">Typname-Element für selectioncondition für entryselectedby für wideentry (Format)</span><span class="sxs-lookup"><span data-stu-id="aa3d6-127">TypeName Element for SelectionCondition for EntrySelectedBy for WideEntry (Format)</span></span>](./typename-element-for-selectioncondition-for-entryselectedby-for-widecontrol-format.md)|<span data-ttu-id="aa3d6-128">Optionales Element.</span><span class="sxs-lookup"><span data-stu-id="aa3d6-128">Optional element.</span></span><br /><br /> <span data-ttu-id="aa3d6-129">Gibt einen .NET-Typ an, der die Bedingung auslöst.</span><span class="sxs-lookup"><span data-stu-id="aa3d6-129">Specifies a .NET type that triggers the condition.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="aa3d6-130">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="aa3d6-130">Parent Elements</span></span>

|<span data-ttu-id="aa3d6-131">Element</span><span class="sxs-lookup"><span data-stu-id="aa3d6-131">Element</span></span>|<span data-ttu-id="aa3d6-132">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="aa3d6-132">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="aa3d6-133">Element „EntrySelectedBy“ für WideEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="aa3d6-133">EntrySelectedBy Element for WideEntry (Format)</span></span>](./entryselectedby-element-for-wideentry-format.md)|<span data-ttu-id="aa3d6-134">Definiert die .NET-Typen, die diesen breiten Eintrag verwenden, oder die Bedingung, die für die Verwendung dieses Eintrags vorhanden sein muss.</span><span class="sxs-lookup"><span data-stu-id="aa3d6-134">Defines the .NET types that use this wide entry or the condition that must exist for this entry to be used.</span></span>|

## <a name="remarks"></a><span data-ttu-id="aa3d6-135">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="aa3d6-135">Remarks</span></span>

<span data-ttu-id="aa3d6-136">Für jeden breiten Eintrag muss mindestens ein Typname, ein Auswahl Satz oder eine Auswahlbedingung definiert sein.</span><span class="sxs-lookup"><span data-stu-id="aa3d6-136">Each wide entry must have at least one type name, selection set, or selection condition defined.</span></span>

<span data-ttu-id="aa3d6-137">Wenn Sie eine Auswahlbedingung definieren, gelten die folgenden Anforderungen:</span><span class="sxs-lookup"><span data-stu-id="aa3d6-137">When you are defining a selection condition, the following requirements apply:</span></span>

- <span data-ttu-id="aa3d6-138">Die Auswahlbedingung muss mindestens einen Eigenschaften Namen oder einen Skriptblock angeben, kann jedoch nicht beides angeben.</span><span class="sxs-lookup"><span data-stu-id="aa3d6-138">The selection condition must specify a least one property name or a script block, but cannot specify both.</span></span>

- <span data-ttu-id="aa3d6-139">Die Auswahlbedingung kann eine beliebige Anzahl von .NET-Typen oder-Auswahl Sätzen angeben, kann jedoch nicht beides angeben.</span><span class="sxs-lookup"><span data-stu-id="aa3d6-139">The selection condition can specify any number of .NET types or selection sets, but cannot specify both.</span></span>

<span data-ttu-id="aa3d6-140">Weitere Informationen zum Verwenden von Auswahl Bedingungen finden Sie unter Definieren von Bedingungen für den Fall, [dass ein Ansichts Eintrag oder Element verwendet wird](./defining-conditions-for-displaying-data.md).</span><span class="sxs-lookup"><span data-stu-id="aa3d6-140">For more information about how to use selection conditions, see [Defining Conditions for when a View Entry or Item is Used](./defining-conditions-for-displaying-data.md).</span></span>

<span data-ttu-id="aa3d6-141">Weitere Informationen zu anderen Komponenten einer breiten Ansicht finden Sie unter [Erstellen einer breiten Ansicht](./creating-a-wide-view.md).</span><span class="sxs-lookup"><span data-stu-id="aa3d6-141">For more information about other components of a wide view, see [Creating a Wide View](./creating-a-wide-view.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="aa3d6-142">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="aa3d6-142">See Also</span></span>

[<span data-ttu-id="aa3d6-143">Erstellen einer breiten Ansicht</span><span class="sxs-lookup"><span data-stu-id="aa3d6-143">Creating a Wide View</span></span>](./creating-a-wide-view.md)

[<span data-ttu-id="aa3d6-144">Definieren von Bedingungen für die Anzeige von Daten</span><span class="sxs-lookup"><span data-stu-id="aa3d6-144">Defining Conditions for When Data Is Displayed</span></span>](./defining-conditions-for-displaying-data.md)

[<span data-ttu-id="aa3d6-145">Element „EntrySelectedBy“ für WideEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="aa3d6-145">EntrySelectedBy Element for WideEntry (Format)</span></span>](./entryselectedby-element-for-wideentry-format.md)

[<span data-ttu-id="aa3d6-146">Element „PropertyName“ für SelectionCondition für EntrySelectedBy für WideEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="aa3d6-146">PropertyName Element for SelectionCondition for EntrySelectedBy for WideEntry (Format)</span></span>](./propertyname-element-for-selectioncondition-for-entryselectedby-for-wideentry-format.md)

[<span data-ttu-id="aa3d6-147">ScriptBlock-Element für selectioncondition für entryselectedby für wideentry (Format)</span><span class="sxs-lookup"><span data-stu-id="aa3d6-147">ScriptBlock Element for SelectionCondition for EntrySelectedBy for WideEntry (Format)</span></span>](./scriptblock-element-for-selectioncondition-for-entryselectedby-for-widecontrol-format.md)

[<span data-ttu-id="aa3d6-148">Element „SelectionSetName“ für SelectionCondition für EntrySelectedBy für WideEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="aa3d6-148">SelectionSetName Element for SelectionCondition for EntrySelectedBy for WideEntry (Format)</span></span>](./selectionsetname-element-for-selectioncondition-for-entryselectedby-for-wideentry-format.md)

[<span data-ttu-id="aa3d6-149">Typname-Element für selectioncondition für entryselectedby für wideentry (Format)</span><span class="sxs-lookup"><span data-stu-id="aa3d6-149">TypeName Element for SelectionCondition for EntrySelectedBy for WideEntry (Format)</span></span>](./typename-element-for-selectioncondition-for-entryselectedby-for-widecontrol-format.md)

[<span data-ttu-id="aa3d6-150">Schreiben einer PowerShell-Formatierungsdatei</span><span class="sxs-lookup"><span data-stu-id="aa3d6-150">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
