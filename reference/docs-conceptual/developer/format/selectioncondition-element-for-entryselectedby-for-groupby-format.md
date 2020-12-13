---
ms.date: 09/13/2016
ms.topic: reference
title: Element „SelectionCondition“ für EntrySelectedBy für GroupBy (Format)
description: Element „SelectionCondition“ für EntrySelectedBy für GroupBy (Format)
ms.openlocfilehash: 14c293b6bc6d6accc201de35be9219349079801d
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92664751"
---
# <a name="selectioncondition-element-for-entryselectedby-for-groupby-format"></a><span data-ttu-id="246c0-103">Element „SelectionCondition“ für EntrySelectedBy für GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="246c0-103">SelectionCondition Element for EntrySelectedBy for GroupBy (Format)</span></span>

<span data-ttu-id="246c0-104">Definiert eine Bedingung, die vorhanden sein muss, damit eine Steuerelement Definition verwendet werden muss.</span><span class="sxs-lookup"><span data-stu-id="246c0-104">Defines a condition that must exist for a control definition to be used.</span></span> <span data-ttu-id="246c0-105">Dieses Element wird verwendet, wenn definiert wird, wie eine neue Gruppe von Objekten angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="246c0-105">This element is used when defining how a new group of objects is displayed.</span></span>

<span data-ttu-id="246c0-106">Configuration-Element (Format) viewdefinitions-Element (Format) Ansichts Element (Format) GroupBy-Element für View (Format) CustomControl-Element für GroupBy (Format) customentries-Element für CustomControl für GroupBy (Format) customentry-Element für CustomControl für GroupBy (Format) entryselectedby-Element für customentry für GroupBy (Format) selectioncondition-Element für entryselectedby für GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="246c0-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) GroupBy Element for View (Format) CustomControl Element for GroupBy (Format) CustomEntries Element for CustomControl for GroupBy (Format) CustomEntry Element for CustomControl for GroupBy (Format) EntrySelectedBy Element for CustomEntry for GroupBy (Format) SelectionCondition Element for EntrySelectedBy for GroupBy (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="246c0-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="246c0-107">Syntax</span></span>

```xml
<SelectionCondition>
  <TypeName>Nameof.NetType</TypeName>
  <SelectionSetName>NameofSelectionSet</SelectionSetName>
  <PropertyName>.NetTypeProperty</PropertyName>
  <ScriptBlock>ScriptToEvaluate</ScriptBlock>
</SelectionCondition>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="246c0-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="246c0-108">Attributes and Elements</span></span>

<span data-ttu-id="246c0-109">In den folgenden Abschnitten werden Attribute, untergeordnete Elemente und das übergeordnete Element des- `SelectionCondition` Elements beschrieben.</span><span class="sxs-lookup"><span data-stu-id="246c0-109">The following sections describe attributes, child elements, and the parent element of the `SelectionCondition` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="246c0-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="246c0-110">Attributes</span></span>

<span data-ttu-id="246c0-111">Keine</span><span class="sxs-lookup"><span data-stu-id="246c0-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="246c0-112">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="246c0-112">Child Elements</span></span>

|<span data-ttu-id="246c0-113">Element</span><span class="sxs-lookup"><span data-stu-id="246c0-113">Element</span></span>|<span data-ttu-id="246c0-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="246c0-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="246c0-115">Element „PropertyName“ für SelectionCondition für GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="246c0-115">PropertyName Element for SelectionCondition for GroupBy (Format)</span></span>](./propertyname-element-for-selectioncondition-for-groupby-format.md)|<span data-ttu-id="246c0-116">Optionales Element.</span><span class="sxs-lookup"><span data-stu-id="246c0-116">Optional element.</span></span><br /><br /> <span data-ttu-id="246c0-117">Gibt eine .net-Eigenschaft an, die die Bedingung auslöst.</span><span class="sxs-lookup"><span data-stu-id="246c0-117">Specifies a .NET property that triggers the condition.</span></span>|
|[<span data-ttu-id="246c0-118">ScriptBlock-Element für selectioncondition für GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="246c0-118">ScriptBlock Element for SelectionCondition for GroupBy (Format)</span></span>](./scriptblock-element-for-selectioncondition-for-entryselectedby-for-groupby-format.md)|<span data-ttu-id="246c0-119">Optionales Element.</span><span class="sxs-lookup"><span data-stu-id="246c0-119">Optional element.</span></span><br /><br /> <span data-ttu-id="246c0-120">Gibt das Skript an, das die Bedingung auslöst.</span><span class="sxs-lookup"><span data-stu-id="246c0-120">Specifies the script that triggers the condition.</span></span>|
|[<span data-ttu-id="246c0-121">Element „SelectionSetName“ für SelectionCondition für GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="246c0-121">SelectionSetName Element for SelectionCondition for GroupBy (Format)</span></span>](./selectionsetname-element-for-selectioncondition-for-groupby-format.md)|<span data-ttu-id="246c0-122">Optionales Element.</span><span class="sxs-lookup"><span data-stu-id="246c0-122">Optional element.</span></span><br /><br /> <span data-ttu-id="246c0-123">Gibt den Satz von .NET-Typen an, der die Bedingung auslöst.</span><span class="sxs-lookup"><span data-stu-id="246c0-123">Specifies the set of .NET types that triggers the condition.</span></span>|
|[<span data-ttu-id="246c0-124">Typname-Element für selectioncondition für GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="246c0-124">TypeName Element for SelectionCondition for GroupBy  (Format)</span></span>](./typename-element-for-selectioncondition-for-groupby-format.md)|<span data-ttu-id="246c0-125">Optionales Element.</span><span class="sxs-lookup"><span data-stu-id="246c0-125">Optional element.</span></span><br /><br /> <span data-ttu-id="246c0-126">Gibt einen .NET-Typ an, der die Bedingung auslöst.</span><span class="sxs-lookup"><span data-stu-id="246c0-126">Specifies a .NET type that triggers the condition.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="246c0-127">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="246c0-127">Parent Elements</span></span>

|<span data-ttu-id="246c0-128">Element</span><span class="sxs-lookup"><span data-stu-id="246c0-128">Element</span></span>|<span data-ttu-id="246c0-129">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="246c0-129">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="246c0-130">Element „EntrySelectedBy“ für CustomEntry für GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="246c0-130">EntrySelectedBy Element for CustomEntry for GroupBy (Format)</span></span>](./entryselectedby-element-for-customentry-for-groupby-format.md)|<span data-ttu-id="246c0-131">Definiert die .NET-Typen, die diese Steuerelement Definition verwenden, oder die Bedingung, die vorhanden sein muss, damit diese Definition verwendet werden muss.</span><span class="sxs-lookup"><span data-stu-id="246c0-131">Defines the .NET types that use this control definition or the condition that must exist for this definition to be used.</span></span>|

## <a name="remarks"></a><span data-ttu-id="246c0-132">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="246c0-132">Remarks</span></span>

<span data-ttu-id="246c0-133">Wenn Sie eine Auswahlbedingung definieren, gelten die folgenden Anforderungen:</span><span class="sxs-lookup"><span data-stu-id="246c0-133">When you are defining a selection condition, the following requirements apply:</span></span>

- <span data-ttu-id="246c0-134">Die Auswahlbedingung muss mindestens einen Eigenschaften Namen oder einen Skriptblock angeben, kann jedoch nicht beides angeben.</span><span class="sxs-lookup"><span data-stu-id="246c0-134">The selection condition must specify a least one property name or a script block, but cannot specify both.</span></span>

- <span data-ttu-id="246c0-135">Die Auswahlbedingung kann eine beliebige Anzahl von .NET-Typen oder-Auswahl Sätzen angeben, kann jedoch nicht beides angeben.</span><span class="sxs-lookup"><span data-stu-id="246c0-135">The selection condition can specify any number of .NET types or selection sets, but cannot specify both.</span></span>

<span data-ttu-id="246c0-136">Weitere Informationen zum Verwenden von Auswahl Bedingungen finden Sie unter [Definieren von Bedingungen für die Anzeige von Daten](./defining-conditions-for-displaying-data.md).</span><span class="sxs-lookup"><span data-stu-id="246c0-136">For more information about how to use selection conditions, see [Defining Conditions for when Data is Displayed](./defining-conditions-for-displaying-data.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="246c0-137">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="246c0-137">See Also</span></span>

[<span data-ttu-id="246c0-138">Element „PropertyName“ für SelectionCondition für CustomControl für View (Format)</span><span class="sxs-lookup"><span data-stu-id="246c0-138">PropertyName Element for SelectionCondition for CustomControl for View (Format)</span></span>](./propertyname-element-for-selectioncondition-for-customcontrol-for-view-format.md)

[<span data-ttu-id="246c0-139">Element „ScriptBlock“ für SelectionCondition für CustomControl für View (Format)</span><span class="sxs-lookup"><span data-stu-id="246c0-139">ScriptBlock Element for SelectionCondition for CustomControl for View (Format)</span></span>](./scriptblock-element-for-selectioncondition-for-customcontrol-for-view-format.md)

[<span data-ttu-id="246c0-140">Selectionsetname-Element für selectioncondition für benutzerdefiniertes Steuer Element für Ansicht (Format)</span><span class="sxs-lookup"><span data-stu-id="246c0-140">SelectionSetName Element for SelectionCondition for Custom Control for View (Format)</span></span>](./selectionsetname-element-for-selectioncondition-for-customcontrol-for-view-format.md)

[<span data-ttu-id="246c0-141">Typname-Element für selectioncondition für GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="246c0-141">TypeName Element for SelectionCondition for GroupBy  (Format)</span></span>](./typename-element-for-selectioncondition-for-groupby-format.md)

[<span data-ttu-id="246c0-142">Element „EntrySelectedBy“ für CustomEntry für GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="246c0-142">EntrySelectedBy Element for CustomEntry for GroupBy (Format)</span></span>](./entryselectedby-element-for-customentry-for-groupby-format.md)

[<span data-ttu-id="246c0-143">Schreiben einer PowerShell-Formatierungsdatei</span><span class="sxs-lookup"><span data-stu-id="246c0-143">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
