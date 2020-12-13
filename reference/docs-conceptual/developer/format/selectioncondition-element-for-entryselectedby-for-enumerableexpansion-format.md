---
ms.date: 09/13/2016
ms.topic: reference
title: Element „SelectionCondition“ für EntrySelectedBy für EnumerableExpansion (Format)
description: Element „SelectionCondition“ für EntrySelectedBy für EnumerableExpansion (Format)
ms.openlocfilehash: 3ecf7fde99b9ee66a153eea416792f351ff62af3
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92647923"
---
# <a name="selectioncondition-element-for-entryselectedby-for-enumerableexpansion-format"></a><span data-ttu-id="79d26-103">Element „SelectionCondition“ für EntrySelectedBy für EnumerableExpansion (Format)</span><span class="sxs-lookup"><span data-stu-id="79d26-103">SelectionCondition Element for EntrySelectedBy for EnumerableExpansion (Format)</span></span>

<span data-ttu-id="79d26-104">Definiert die Bedingung, die vorhanden sein muss, um die Auflistungs Objekte dieser Definition zu erweitern.</span><span class="sxs-lookup"><span data-stu-id="79d26-104">Defines the condition that must exist to expand the collection objects of this definition.</span></span>

<span data-ttu-id="79d26-105">Configuration-Element (Format) DefaultSettings-Element (Format) enumerableweiterung-Element (Format) enumerableweiterung-Element (Format) entryselectedby-Element für enumerableexpansion (Format) selectioncondition-Element für entryselectedby für enumerableexpansion (Format)</span><span class="sxs-lookup"><span data-stu-id="79d26-105">Configuration Element (Format) DefaultSettings Element (Format) EnumerableExpansions Element (Format) EnumerableExpansion Element (Format) EntrySelectedBy Element for EnumerableExpansion (Format) SelectionCondition Element for EntrySelectedBy for EnumerableExpansion (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="79d26-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="79d26-106">Syntax</span></span>

```xml
<SelectionCondition>
  <TypeName>Nameof.NetType</TypeName>
  <SelectionSetName>NameofSelectionSet</SelectionSetName>
  <PropertyName>.NetTypeProperty</PropertyName>
  <ScriptBlock>ScriptToEvaluate</ScriptBlock>
</SelectionCondition>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="79d26-107">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="79d26-107">Attributes and Elements</span></span>

<span data-ttu-id="79d26-108">In den folgenden Abschnitten werden Attribute, untergeordnete Elemente und das übergeordnete Element des- `SelectionCondition` Elements beschrieben.</span><span class="sxs-lookup"><span data-stu-id="79d26-108">The following sections describe attributes, child elements, and the parent element of the `SelectionCondition` element.</span></span> <span data-ttu-id="79d26-109">Sie müssen ein einzelnes- `PropertyName` oder- `ScriptBlock` Element angeben.</span><span class="sxs-lookup"><span data-stu-id="79d26-109">You must specify a single `PropertyName` or `ScriptBlock` element.</span></span> <span data-ttu-id="79d26-110">Das `SelectionSetName` -Element und das- `TypeName` Element sind optional.</span><span class="sxs-lookup"><span data-stu-id="79d26-110">The `SelectionSetName` and `TypeName` elements are optional.</span></span> <span data-ttu-id="79d26-111">Sie können eines der beiden Elemente angeben.</span><span class="sxs-lookup"><span data-stu-id="79d26-111">You can specify one of either element.</span></span>

### <a name="attributes"></a><span data-ttu-id="79d26-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="79d26-112">Attributes</span></span>

<span data-ttu-id="79d26-113">Keine</span><span class="sxs-lookup"><span data-stu-id="79d26-113">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="79d26-114">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="79d26-114">Child Elements</span></span>

|<span data-ttu-id="79d26-115">Element</span><span class="sxs-lookup"><span data-stu-id="79d26-115">Element</span></span>|<span data-ttu-id="79d26-116">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="79d26-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="79d26-117">Element „PropertyName“ für SelectionCondition für EntrySelectedBy für EnumerableExpansion (Format)</span><span class="sxs-lookup"><span data-stu-id="79d26-117">PropertyName Element for SelectionCondition for EntrySelectedBy for EnumerableExpansion (Format)</span></span>](./propertyname-element-for-selectioncondition-for-entryselectedby-for-enumerableexpansion-format.md)|<span data-ttu-id="79d26-118">Optionales Element.</span><span class="sxs-lookup"><span data-stu-id="79d26-118">Optional element.</span></span><br /><br /> <span data-ttu-id="79d26-119">Gibt die .net-Eigenschaft an, die die Bedingung auslöst.</span><span class="sxs-lookup"><span data-stu-id="79d26-119">Specifies the .NET property that triggers the condition.</span></span>|
|[<span data-ttu-id="79d26-120">Element „ScriptBlock“ für SelectionCondition für EntrySelectedBy für EnumerableExpansion (Format)</span><span class="sxs-lookup"><span data-stu-id="79d26-120">ScriptBlock Element for SelectionCondition for EntrySelectedBy for EnumerableExpansion (Format)</span></span>](./scriptblock-element-for-selectioncondition-for-entryselectedby-for-enumerableexpansion-format.md)|<span data-ttu-id="79d26-121">Optionales Element.</span><span class="sxs-lookup"><span data-stu-id="79d26-121">Optional element.</span></span><br /><br /> <span data-ttu-id="79d26-122">Gibt das Skript an, das die Bedingung auslöst.</span><span class="sxs-lookup"><span data-stu-id="79d26-122">Specifies the script that triggers the condition.</span></span>|
|[<span data-ttu-id="79d26-123">Element „SelectionSetName“ für SelectionCondition für EntrySelectedBy für EnumerableExpansion (Format)</span><span class="sxs-lookup"><span data-stu-id="79d26-123">SelectionSetName Element for SelectionCondition for EntrySelectedBy for EnumerableExpansion (Format)</span></span>](./selectionsetname-element-for-selectioncondition-for-entryselectedby-for-enumerableexpansion-format.md)|<span data-ttu-id="79d26-124">Optionales Element.</span><span class="sxs-lookup"><span data-stu-id="79d26-124">Optional element.</span></span><br /><br /> <span data-ttu-id="79d26-125">Gibt den Satz von .NET-Typen an, der die Bedingung auslöst.</span><span class="sxs-lookup"><span data-stu-id="79d26-125">Specifies the set of .NET types that triggers the condition.</span></span>|
|[<span data-ttu-id="79d26-126">Element „TypeName“ für SelectionCondition für EntrySelectedBy für EnumerableExpansion (Format)</span><span class="sxs-lookup"><span data-stu-id="79d26-126">TypeName Element for SelectionCondition for EntrySelectedBy for EnumerableExpansion (Format)</span></span>](./typename-element-for-selectioncondition-for-entryselectedby-for-enumerableexpansion-format.md)|<span data-ttu-id="79d26-127">Optionales Element.</span><span class="sxs-lookup"><span data-stu-id="79d26-127">Optional element.</span></span><br /><br /> <span data-ttu-id="79d26-128">Gibt einen .NET-Typ an, der die Bedingung auslöst.</span><span class="sxs-lookup"><span data-stu-id="79d26-128">Specifies a .NET type that triggers the condition.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="79d26-129">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="79d26-129">Parent Elements</span></span>

|<span data-ttu-id="79d26-130">Element</span><span class="sxs-lookup"><span data-stu-id="79d26-130">Element</span></span>|<span data-ttu-id="79d26-131">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="79d26-131">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="79d26-132">Element „EntrySelectedBy“ für EnumerableExpansion (Format)</span><span class="sxs-lookup"><span data-stu-id="79d26-132">EntrySelectedBy Element for EnumerableExpansion (Format)</span></span>](./entryselectedby-element-for-enumerableexpansion-format.md)|<span data-ttu-id="79d26-133">Definiert, welche .net-Auflistungs Objekte durch diese Definition erweitert werden.</span><span class="sxs-lookup"><span data-stu-id="79d26-133">Defines which .NET collection objects are expanded by this definition.</span></span>|

## <a name="remarks"></a><span data-ttu-id="79d26-134">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="79d26-134">Remarks</span></span>

<span data-ttu-id="79d26-135">Für jede Definition muss mindestens ein Typname, ein Auswahl Satz oder eine Auswahlbedingung definiert sein.</span><span class="sxs-lookup"><span data-stu-id="79d26-135">Each definition must have at least one type name, selection set, or selection condition defined.</span></span>

<span data-ttu-id="79d26-136">Wenn Sie eine Auswahlbedingung definieren, gelten die folgenden Anforderungen:</span><span class="sxs-lookup"><span data-stu-id="79d26-136">When you are defining a selection condition, the following requirements apply:</span></span>

- <span data-ttu-id="79d26-137">Die Auswahlbedingung muss mindestens einen Eigenschaften Namen oder einen Skriptblock angeben, kann jedoch nicht beides angeben.</span><span class="sxs-lookup"><span data-stu-id="79d26-137">The selection condition must specify a least one property name or a script block, but cannot specify both.</span></span>

- <span data-ttu-id="79d26-138">Die Auswahlbedingung kann eine beliebige Anzahl von .NET-Typen oder-Auswahl Sätzen angeben, kann jedoch nicht beides angeben.</span><span class="sxs-lookup"><span data-stu-id="79d26-138">The selection condition can specify any number of .NET types or selection sets, but cannot specify both.</span></span>

<span data-ttu-id="79d26-139">Weitere Informationen zum Verwenden von Auswahl Bedingungen finden Sie unter [Definieren von Bedingungen für die Wiedergabe von Daten](./defining-conditions-for-displaying-data.md).</span><span class="sxs-lookup"><span data-stu-id="79d26-139">For more information about how to use selection conditions, see [Defining Conditions for Diplaying Data](./defining-conditions-for-displaying-data.md).</span></span>

<span data-ttu-id="79d26-140">Weitere Informationen zu anderen Komponenten einer breiten Ansicht finden Sie unter [Wide View](./creating-a-wide-view.md).</span><span class="sxs-lookup"><span data-stu-id="79d26-140">For more information about other components of a wide view, see [Wide View](./creating-a-wide-view.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="79d26-141">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="79d26-141">See Also</span></span>

[<span data-ttu-id="79d26-142">Definieren von Bedingungen für die Anzeige von Daten</span><span class="sxs-lookup"><span data-stu-id="79d26-142">Defining Conditions for When Data Is Displayed</span></span>](./defining-conditions-for-displaying-data.md)

[<span data-ttu-id="79d26-143">Schreiben einer PowerShell-Formatierungsdatei</span><span class="sxs-lookup"><span data-stu-id="79d26-143">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
