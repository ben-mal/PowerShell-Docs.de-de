---
ms.date: 09/13/2016
ms.topic: reference
title: Element „SelectionCondition“ für EntrySelectedBy für CustomControl (Format)
description: Element „SelectionCondition“ für EntrySelectedBy für CustomControl (Format)
ms.openlocfilehash: 6d4cc5a2d5fef0445d586e320b3729d3a7044063
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92649776"
---
# <a name="selectioncondition-element-for-entryselectedby-for-customcontrol-format"></a><span data-ttu-id="e0dd4-103">Element „SelectionCondition“ für EntrySelectedBy für CustomControl (Format)</span><span class="sxs-lookup"><span data-stu-id="e0dd4-103">SelectionCondition Element for EntrySelectedBy for CustomControl (Format)</span></span>

<span data-ttu-id="e0dd4-104">Definiert eine Bedingung, die vorhanden sein muss, damit eine Steuerelement Definition verwendet werden muss.</span><span class="sxs-lookup"><span data-stu-id="e0dd4-104">Defines a condition that must exist for a control definition to be used.</span></span> <span data-ttu-id="e0dd4-105">Dieses Element wird beim Definieren einer benutzerdefinierten Steuerelement Ansicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="e0dd4-105">This element is used when defining a custom control view.</span></span>

<span data-ttu-id="e0dd4-106">Konfigurationselement (Format) viewdefinitions-Element (Format) View-Element (Format) CustomControl-Element für View (Format) customentries-Element für CustomControl for View (Format) customentry-Element für customentries für CustomControl for View (Format) customItem-Element für customentry für CustomControl für das View (Format) entryselectedby-Element für customentry für CustomControl für View (Format) selectioncondition-Element für entryselectedby für CustomControl for View (Format)</span><span class="sxs-lookup"><span data-stu-id="e0dd4-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) CustomControl Element for View (Format) CustomEntries Element for CustomControl for View (Format) CustomEntry Element for CustomEntries for CustomControl for View (Format) CustomItem Element for CustomEntry for CustomControl for View (Format) EntrySelectedBy Element for CustomEntry for CustomControl for View (Format) SelectionCondition Element for EntrySelectedBy for CustomControl for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="e0dd4-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="e0dd4-107">Syntax</span></span>

```xml
<SelectionCondition>
  <TypeName>Nameof.NetType</TypeName>
  <SelectionSetName>NameofSelectionSet</SelectionSetName>
  <PropertyName>.NetTypeProperty</PropertyName>
  <ScriptBlock>ScriptToEvaluate</ScriptBlock>
</SelectionCondition>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="e0dd4-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="e0dd4-108">Attributes and Elements</span></span>

<span data-ttu-id="e0dd4-109">In den folgenden Abschnitten werden Attribute, untergeordnete Elemente und das übergeordnete Element des- `SelectionCondition` Elements beschrieben.</span><span class="sxs-lookup"><span data-stu-id="e0dd4-109">The following sections describe attributes, child elements, and the parent element of the `SelectionCondition` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="e0dd4-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="e0dd4-110">Attributes</span></span>

<span data-ttu-id="e0dd4-111">Keine</span><span class="sxs-lookup"><span data-stu-id="e0dd4-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="e0dd4-112">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="e0dd4-112">Child Elements</span></span>

|<span data-ttu-id="e0dd4-113">Element</span><span class="sxs-lookup"><span data-stu-id="e0dd4-113">Element</span></span>|<span data-ttu-id="e0dd4-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e0dd4-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="e0dd4-115">Element „PropertyName“ für SelectionCondition für CustomControl für View (Format)</span><span class="sxs-lookup"><span data-stu-id="e0dd4-115">PropertyName Element for SelectionCondition for CustomControl for View (Format)</span></span>](./propertyname-element-for-selectioncondition-for-customcontrol-for-view-format.md)|<span data-ttu-id="e0dd4-116">Optionales Element.</span><span class="sxs-lookup"><span data-stu-id="e0dd4-116">Optional element.</span></span><br /><br /> <span data-ttu-id="e0dd4-117">Gibt eine .net-Eigenschaft an, die die Bedingung auslöst.</span><span class="sxs-lookup"><span data-stu-id="e0dd4-117">Specifies a .NET property that triggers the condition.</span></span>|
|[<span data-ttu-id="e0dd4-118">Element „ScriptBlock“ für SelectionCondition für CustomControl für View (Format)</span><span class="sxs-lookup"><span data-stu-id="e0dd4-118">ScriptBlock Element for SelectionCondition for CustomControl for View (Format)</span></span>](./scriptblock-element-for-selectioncondition-for-customcontrol-for-view-format.md)|<span data-ttu-id="e0dd4-119">Optionales Element.</span><span class="sxs-lookup"><span data-stu-id="e0dd4-119">Optional element.</span></span><br /><br /> <span data-ttu-id="e0dd4-120">Gibt das Skript an, das die Bedingung auslöst.</span><span class="sxs-lookup"><span data-stu-id="e0dd4-120">Specifies the script that triggers the condition.</span></span>|
|[<span data-ttu-id="e0dd4-121">Selectionsetname-Element für selectioncondition für benutzerdefiniertes Steuer Element für Ansicht (Format)</span><span class="sxs-lookup"><span data-stu-id="e0dd4-121">SelectionSetName Element for SelectionCondition for Custom Control for View (Format)</span></span>](./selectionsetname-element-for-selectioncondition-for-customcontrol-for-view-format.md)|<span data-ttu-id="e0dd4-122">Optionales Element.</span><span class="sxs-lookup"><span data-stu-id="e0dd4-122">Optional element.</span></span><br /><br /> <span data-ttu-id="e0dd4-123">Gibt den Satz von .NET-Typen an, der die Bedingung auslöst.</span><span class="sxs-lookup"><span data-stu-id="e0dd4-123">Specifies the set of .NET types that triggers the condition.</span></span>|
|[<span data-ttu-id="e0dd4-124">Element „TypeName“ für SelectionCondition für CustomControl für View (Format)</span><span class="sxs-lookup"><span data-stu-id="e0dd4-124">TypeName Element for SelectionCondition for CustomControl for View  (Format)</span></span>](./typename-element-for-selectioncondition-for-customcontrol-for-view-format.md)|<span data-ttu-id="e0dd4-125">Optionales Element.</span><span class="sxs-lookup"><span data-stu-id="e0dd4-125">Optional element.</span></span><br /><br /> <span data-ttu-id="e0dd4-126">Gibt einen .NET-Typ an, der die Bedingung auslöst.</span><span class="sxs-lookup"><span data-stu-id="e0dd4-126">Specifies a .NET type that triggers the condition.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="e0dd4-127">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="e0dd4-127">Parent Elements</span></span>

|<span data-ttu-id="e0dd4-128">Element</span><span class="sxs-lookup"><span data-stu-id="e0dd4-128">Element</span></span>|<span data-ttu-id="e0dd4-129">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e0dd4-129">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="e0dd4-130">Element „EntrySelectedBy“ für CustomEntry für CustomControl für View (Format)</span><span class="sxs-lookup"><span data-stu-id="e0dd4-130">EntrySelectedBy Element for CustomEntry for CustomControl for View (Format)</span></span>](./entryselectedby-element-for-customentry-for-customcontrol-for-view-format.md)|<span data-ttu-id="e0dd4-131">Definiert die .NET-Typen, die diese Steuerelement Definition verwenden, oder die Bedingung, die vorhanden sein muss, damit diese Definition verwendet werden muss.</span><span class="sxs-lookup"><span data-stu-id="e0dd4-131">Defines the .NET types that use this control definition or the condition that must exist for this definition to be used.</span></span>|

## <a name="remarks"></a><span data-ttu-id="e0dd4-132">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="e0dd4-132">Remarks</span></span>

<span data-ttu-id="e0dd4-133">Wenn Sie eine Auswahlbedingung definieren, gelten die folgenden Anforderungen:</span><span class="sxs-lookup"><span data-stu-id="e0dd4-133">When you are defining a selection condition, the following requirements apply:</span></span>

- <span data-ttu-id="e0dd4-134">Die Auswahlbedingung muss mindestens einen Eigenschaften Namen oder einen Skriptblock angeben, kann jedoch nicht beides angeben.</span><span class="sxs-lookup"><span data-stu-id="e0dd4-134">The selection condition must specify a least one property name or a script block, but cannot specify both.</span></span>

- <span data-ttu-id="e0dd4-135">Die Auswahlbedingung kann eine beliebige Anzahl von .NET-Typen oder-Auswahl Sätzen angeben, kann jedoch nicht beides angeben.</span><span class="sxs-lookup"><span data-stu-id="e0dd4-135">The selection condition can specify any number of .NET types or selection sets, but cannot specify both.</span></span>

<span data-ttu-id="e0dd4-136">Weitere Informationen zum Verwenden von Auswahl Bedingungen finden Sie unter [Definieren von Bedingungen für die Anzeige von Daten](./defining-conditions-for-displaying-data.md).</span><span class="sxs-lookup"><span data-stu-id="e0dd4-136">For more information about how to use selection conditions, see [Defining Conditions for when Data is Displayed](./defining-conditions-for-displaying-data.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="e0dd4-137">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="e0dd4-137">See Also</span></span>

[<span data-ttu-id="e0dd4-138">Element „PropertyName“ für SelectionCondition für CustomControl für View (Format)</span><span class="sxs-lookup"><span data-stu-id="e0dd4-138">PropertyName Element for SelectionCondition for CustomControl for View (Format)</span></span>](./propertyname-element-for-selectioncondition-for-customcontrol-for-view-format.md)

[<span data-ttu-id="e0dd4-139">Element „ScriptBlock“ für SelectionCondition für CustomControl für View (Format)</span><span class="sxs-lookup"><span data-stu-id="e0dd4-139">ScriptBlock Element for SelectionCondition for CustomControl for View (Format)</span></span>](./scriptblock-element-for-selectioncondition-for-customcontrol-for-view-format.md)

[<span data-ttu-id="e0dd4-140">Selectionsetname-Element für selectioncondition für benutzerdefiniertes Steuer Element für Ansicht (Format)</span><span class="sxs-lookup"><span data-stu-id="e0dd4-140">SelectionSetName Element for SelectionCondition for Custom Control for View (Format)</span></span>](./selectionsetname-element-for-selectioncondition-for-customcontrol-for-view-format.md)

[<span data-ttu-id="e0dd4-141">Element „TypeName“ für SelectionCondition für CustomControl für View (Format)</span><span class="sxs-lookup"><span data-stu-id="e0dd4-141">TypeName Element for SelectionCondition for CustomControl for View  (Format)</span></span>](./typename-element-for-selectioncondition-for-customcontrol-for-view-format.md)

[<span data-ttu-id="e0dd4-142">Element „EntrySelectedBy“ für CustomEntry für CustomControl für View (Format)</span><span class="sxs-lookup"><span data-stu-id="e0dd4-142">EntrySelectedBy Element for CustomEntry for CustomControl for View (Format)</span></span>](./entryselectedby-element-for-customentry-for-customcontrol-for-view-format.md)

[<span data-ttu-id="e0dd4-143">Schreiben einer PowerShell-Formatierungsdatei</span><span class="sxs-lookup"><span data-stu-id="e0dd4-143">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
