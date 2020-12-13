---
ms.date: 09/13/2016
ms.topic: reference
title: Element „SelectionCondition“ für EntrySelectedBy für Controls für View (Format)
description: Element „SelectionCondition“ für EntrySelectedBy für Controls für View (Format)
ms.openlocfilehash: 16b048e73195b3d6168724714ff223851dc1b20b
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92664854"
---
# <a name="selectioncondition-element-for-entryselectedby-for-controls-for-view-format"></a><span data-ttu-id="a7b8f-103">Element „SelectionCondition“ für EntrySelectedBy für Controls für View (Format)</span><span class="sxs-lookup"><span data-stu-id="a7b8f-103">SelectionCondition Element for EntrySelectedBy for Controls for View (Format)</span></span>

<span data-ttu-id="a7b8f-104">Definiert eine Bedingung, die vorhanden sein muss, damit die Steuerelement Definition verwendet werden muss.</span><span class="sxs-lookup"><span data-stu-id="a7b8f-104">Defines a condition that must exist for the control definition to be used.</span></span> <span data-ttu-id="a7b8f-105">Dieses Element wird beim Definieren von Steuerelementen verwendet, die von einer Ansicht verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="a7b8f-105">This element is used when defining controls that can be used by a view.</span></span>

<span data-ttu-id="a7b8f-106">Konfigurationselement (Format) viewdefinitions-Element (Format) Ansichts Element (Format) steuert Element (Format) Steuerelement für Steuerelemente für Ansicht (Format) CustomControl-Element für Steuerelemente für das View (Format) customentries-Element für CustomControl für Steuerelemente View (Format) customentry-Element für customentries für Steuerelemente für das View (Format) entryselectedby-Element für customentry für Steuerelemente für View (Format) selectioncondition-Element für entryselectedby für Steuerelemente für View (Format)</span><span class="sxs-lookup"><span data-stu-id="a7b8f-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) Controls Element (Format) Control Element for Controls for View (Format) CustomControl Element for Control for Controls for View (Format) CustomEntries Element for CustomControl for Controls for View (Format) CustomEntry Element for CustomEntries for Controls for View (Format) EntrySelectedBy Element for CustomEntry for Controls for View (Format) SelectionCondition Element for EntrySelectedBy for Controls for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="a7b8f-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="a7b8f-107">Syntax</span></span>

```xml
<SelectionCondition>
  <TypeName>Nameof.NetType</TypeName>
  <SelectionSetName>NameofSelectionSet</SelectionSetName>
  <PropertyName>.NetTypeProperty</PropertyName>
  <ScriptBlock>ScriptToEvaluate</ScriptBlock>
</SelectionCondition>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="a7b8f-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="a7b8f-108">Attributes and Elements</span></span>

<span data-ttu-id="a7b8f-109">In den folgenden Abschnitten werden Attribute, untergeordnete Elemente und das übergeordnete Element des- `SelectionCondition` Elements beschrieben.</span><span class="sxs-lookup"><span data-stu-id="a7b8f-109">The following sections describe attributes, child elements, and the parent element of the `SelectionCondition` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="a7b8f-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="a7b8f-110">Attributes</span></span>

<span data-ttu-id="a7b8f-111">Keine</span><span class="sxs-lookup"><span data-stu-id="a7b8f-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="a7b8f-112">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="a7b8f-112">Child Elements</span></span>

|<span data-ttu-id="a7b8f-113">Element</span><span class="sxs-lookup"><span data-stu-id="a7b8f-113">Element</span></span>|<span data-ttu-id="a7b8f-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a7b8f-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="a7b8f-115">Element „PropertyName“ für SelectionCondition für Controls für View (Format)</span><span class="sxs-lookup"><span data-stu-id="a7b8f-115">PropertyName Element for SelectionCondition for Controls for View (Format)</span></span>](./propertyname-element-for-selectioncondition-for-controls-for-view-format.md)|<span data-ttu-id="a7b8f-116">Optionales Element.</span><span class="sxs-lookup"><span data-stu-id="a7b8f-116">Optional element.</span></span><br /><br /> <span data-ttu-id="a7b8f-117">Gibt eine .net-Eigenschaft an, die die Bedingung auslöst.</span><span class="sxs-lookup"><span data-stu-id="a7b8f-117">Specifies a .NET property that triggers the condition.</span></span>|
|[<span data-ttu-id="a7b8f-118">Element „ScriptBlock“ für SelectionCondition für Controls für View (Format)</span><span class="sxs-lookup"><span data-stu-id="a7b8f-118">ScriptBlock Element for SelectionCondition for Controls for View (Format)</span></span>](./scriptblock-element-for-selectioncondition-for-controls-for-view-format.md)|<span data-ttu-id="a7b8f-119">Optionales Element.</span><span class="sxs-lookup"><span data-stu-id="a7b8f-119">Optional element.</span></span><br /><br /> <span data-ttu-id="a7b8f-120">Gibt das Skript an, das die Bedingung auslöst.</span><span class="sxs-lookup"><span data-stu-id="a7b8f-120">Specifies the script that triggers the condition.</span></span>|
|[<span data-ttu-id="a7b8f-121">Element „SelectionSetName“ für SelectionCondition für Controls für View (Format)</span><span class="sxs-lookup"><span data-stu-id="a7b8f-121">SelectionSetName Element for SelectionCondition for Controls for View (Format)</span></span>](./selectionsetname-element-for-selectioncondition-for-controls-for-view-format.md)|<span data-ttu-id="a7b8f-122">Optionales Element.</span><span class="sxs-lookup"><span data-stu-id="a7b8f-122">Optional element.</span></span><br /><br /> <span data-ttu-id="a7b8f-123">Gibt den Satz von .NET-Typen an, der die Bedingung auslöst.</span><span class="sxs-lookup"><span data-stu-id="a7b8f-123">Specifies the set of .NET types that triggers the condition.</span></span>|
|[<span data-ttu-id="a7b8f-124">Element „TypeName“ für SelectionCondition für Controls für View (Format)</span><span class="sxs-lookup"><span data-stu-id="a7b8f-124">TypeName Element for SelectionCondition for Controls for View (Format)</span></span>](./typename-element-for-selectioncondition-for-controls-for-view-format.md)|<span data-ttu-id="a7b8f-125">Optionales Element.</span><span class="sxs-lookup"><span data-stu-id="a7b8f-125">Optional element.</span></span><br /><br /> <span data-ttu-id="a7b8f-126">Gibt einen .NET-Typ an, der die Bedingung auslöst.</span><span class="sxs-lookup"><span data-stu-id="a7b8f-126">Specifies a .NET type that triggers the condition.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="a7b8f-127">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="a7b8f-127">Parent Elements</span></span>

|<span data-ttu-id="a7b8f-128">Element</span><span class="sxs-lookup"><span data-stu-id="a7b8f-128">Element</span></span>|<span data-ttu-id="a7b8f-129">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a7b8f-129">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="a7b8f-130">Element „EntrySelectedBy“ für CustomEntry für Controls für View (Format)</span><span class="sxs-lookup"><span data-stu-id="a7b8f-130">EntrySelectedBy Element for CustomEntry for Controls for View (Format)</span></span>](./entryselectedby-element-for-customentry-for-controls-for-view-format.md)|<span data-ttu-id="a7b8f-131">Definiert die .NET-Typen, die diese Steuerelement Definition verwenden, oder die Bedingung, die vorhanden sein muss, damit diese Definition verwendet werden muss.</span><span class="sxs-lookup"><span data-stu-id="a7b8f-131">Defines the .NET types that use this control definition or the condition that must exist for this definition to be used.</span></span>|

## <a name="remarks"></a><span data-ttu-id="a7b8f-132">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="a7b8f-132">Remarks</span></span>

<span data-ttu-id="a7b8f-133">Wenn Sie eine Auswahlbedingung definieren, gelten die folgenden Anforderungen:</span><span class="sxs-lookup"><span data-stu-id="a7b8f-133">When you are defining a selection condition, the following requirements apply:</span></span>

- <span data-ttu-id="a7b8f-134">Die Auswahlbedingung muss mindestens einen Eigenschaften Namen oder einen Skriptblock angeben, kann jedoch nicht beides angeben.</span><span class="sxs-lookup"><span data-stu-id="a7b8f-134">The selection condition must specify a least one property name or a script block, but cannot specify both.</span></span>

- <span data-ttu-id="a7b8f-135">Die Auswahlbedingung kann eine beliebige Anzahl von .NET-Typen oder-Auswahl Sätzen angeben, kann jedoch nicht beides angeben.</span><span class="sxs-lookup"><span data-stu-id="a7b8f-135">The selection condition can specify any number of .NET types or selection sets, but cannot specify both.</span></span>

<span data-ttu-id="a7b8f-136">Weitere Informationen zum Verwenden von Auswahl Bedingungen finden Sie unter [Definieren von Bedingungen für die Anzeige von Daten](./defining-conditions-for-displaying-data.md).</span><span class="sxs-lookup"><span data-stu-id="a7b8f-136">For more information about how to use selection conditions, see [Defining Conditions for when Data is Displayed](./defining-conditions-for-displaying-data.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="a7b8f-137">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="a7b8f-137">See Also</span></span>

[<span data-ttu-id="a7b8f-138">Element „PropertyName“ für SelectionCondition für Controls für View (Format)</span><span class="sxs-lookup"><span data-stu-id="a7b8f-138">PropertyName Element for SelectionCondition for Controls for View (Format)</span></span>](./propertyname-element-for-selectioncondition-for-controls-for-view-format.md)

[<span data-ttu-id="a7b8f-139">Element „ScriptBlock“ für SelectionCondition für Controls für View (Format)</span><span class="sxs-lookup"><span data-stu-id="a7b8f-139">ScriptBlock Element for SelectionCondition for Controls for View (Format)</span></span>](./scriptblock-element-for-selectioncondition-for-controls-for-view-format.md)

[<span data-ttu-id="a7b8f-140">Element „SelectionSetName“ für SelectionCondition für Controls für View (Format)</span><span class="sxs-lookup"><span data-stu-id="a7b8f-140">SelectionSetName Element for SelectionCondition for Controls for View (Format)</span></span>](./selectionsetname-element-for-selectioncondition-for-controls-for-view-format.md)

[<span data-ttu-id="a7b8f-141">Element „TypeName“ für SelectionCondition für Controls für View (Format)</span><span class="sxs-lookup"><span data-stu-id="a7b8f-141">TypeName Element for SelectionCondition for Controls for View (Format)</span></span>](./typename-element-for-selectioncondition-for-controls-for-view-format.md)

[<span data-ttu-id="a7b8f-142">Element „EntrySelectedBy“ für CustomEntry für Controls für View (Format)</span><span class="sxs-lookup"><span data-stu-id="a7b8f-142">EntrySelectedBy Element for CustomEntry for Controls for View (Format)</span></span>](./entryselectedby-element-for-customentry-for-controls-for-view-format.md)

[<span data-ttu-id="a7b8f-143">Schreiben einer PowerShell-Formatierungsdatei</span><span class="sxs-lookup"><span data-stu-id="a7b8f-143">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
