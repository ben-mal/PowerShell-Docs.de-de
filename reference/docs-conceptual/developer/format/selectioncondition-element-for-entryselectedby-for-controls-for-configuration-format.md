---
ms.date: 09/13/2016
ms.topic: reference
title: Element „SelectionCondition“ für EntrySelectedBy für Controls für Configuration (Format)
description: Element „SelectionCondition“ für EntrySelectedBy für Controls für Configuration (Format)
ms.openlocfilehash: ce00cdf868a3075875043aeb59f2cb8a17d049a9
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92645785"
---
# <a name="selectioncondition-element-for-entryselectedby-for-controls-for-configuration-format"></a><span data-ttu-id="9092d-103">Element „SelectionCondition“ für EntrySelectedBy für Controls für Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="9092d-103">SelectionCondition Element for EntrySelectedBy for Controls for Configuration (Format)</span></span>

<span data-ttu-id="9092d-104">Definiert eine Bedingung, die vorhanden sein muss, damit eine allgemeine Steuerelement Definition verwendet werden muss.</span><span class="sxs-lookup"><span data-stu-id="9092d-104">Defines a condition that must exist for a common control definition to be used.</span></span> <span data-ttu-id="9092d-105">Dieses Element wird verwendet, wenn ein gemeinsames Steuerelement definiert wird, das von allen Sichten in der Formatierungs Datei verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="9092d-105">This element is used when defining a common control that can be used by all the views in the formatting file.</span></span>

<span data-ttu-id="9092d-106">Konfigurationselement (Format) Controls-Element des Configuration (Format)-Steuer Elements für Steuerelemente für Konfiguration (Format) CustomControl-Element für Steuerelement für Configuration (Format) customentries-Element für CustomControl für Steuerelemente für Konfiguration (Format) customentry-Element für CustomControl für Steuerelemente für das Configuration (Format) entryselectedby-Element für customentry for Controls for Configuration (Format) selectioncondition-Element für entryselectedby für customentry for Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="9092d-106">Configuration Element (Format) Controls Element of Configuration (Format) Control Element for Controls for Configuration (Format) CustomControl Element for Control for Configuration (Format) CustomEntries Element for CustomControl for Controls for Configuration (Format) CustomEntry Element for CustomControl for Controls for Configuration (Format) EntrySelectedBy Element for CustomEntry for Controls for Configuration (Format) SelectionCondition Element for EntrySelectedBy for CustomEntry for Configuration (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="9092d-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="9092d-107">Syntax</span></span>

```xml
<SelectionCondition>
  <TypeName>Nameof.NetType</TypeName>
  <SelectionSetName>NameofSelectionSet</SelectionSetName>
  <PropertyName>.NetTypeProperty</PropertyName>
  <ScriptBlock>ScriptToEvaluate</ScriptBlock>
</SelectionCondition>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="9092d-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="9092d-108">Attributes and Elements</span></span>

<span data-ttu-id="9092d-109">In den folgenden Abschnitten werden Attribute, untergeordnete Elemente und das übergeordnete Element des- `SelectionCondition` Elements beschrieben.</span><span class="sxs-lookup"><span data-stu-id="9092d-109">The following sections describe attributes, child elements, and the parent element of the `SelectionCondition` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="9092d-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="9092d-110">Attributes</span></span>

<span data-ttu-id="9092d-111">Keine</span><span class="sxs-lookup"><span data-stu-id="9092d-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="9092d-112">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="9092d-112">Child Elements</span></span>

|<span data-ttu-id="9092d-113">Element</span><span class="sxs-lookup"><span data-stu-id="9092d-113">Element</span></span>|<span data-ttu-id="9092d-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9092d-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="9092d-115">Element „PropertyName“ für SelectionCondition für Controls für Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="9092d-115">PropertyName Element for SelectionCondition for Controls for Configuration (Format)</span></span>](./propertyname-element-for-selectioncondition-for-controls-for-configuration-format.md)|<span data-ttu-id="9092d-116">Optionales Element.</span><span class="sxs-lookup"><span data-stu-id="9092d-116">Optional element.</span></span><br /><br /> <span data-ttu-id="9092d-117">Gibt eine .net-Eigenschaft an, die die Bedingung auslöst.</span><span class="sxs-lookup"><span data-stu-id="9092d-117">Specifies a .NET property that triggers the condition.</span></span>|
|[<span data-ttu-id="9092d-118">Element „ScriptBlock“ für SelectionCondition für Controls für Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="9092d-118">ScriptBlock Element for SelectionCondition for Controls for Configuration (Format)</span></span>](./scriptblock-element-for-selectioncondition-for-controls-for-configuration-format.md)|<span data-ttu-id="9092d-119">Optionales Element.</span><span class="sxs-lookup"><span data-stu-id="9092d-119">Optional element.</span></span><br /><br /> <span data-ttu-id="9092d-120">Gibt das Skript an, das die Bedingung auslöst.</span><span class="sxs-lookup"><span data-stu-id="9092d-120">Specifies the script that triggers the condition.</span></span>|
|[<span data-ttu-id="9092d-121">Element „SelectionSetName“ für SelectionCondition für Controls für Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="9092d-121">SelectionSetName Element for SelectionCondition for Controls for Configuration (Format)</span></span>](./selectionsetname-element-for-selectioncondition-for-controls-for-configuration-format.md)|<span data-ttu-id="9092d-122">Optionales Element.</span><span class="sxs-lookup"><span data-stu-id="9092d-122">Optional element.</span></span><br /><br /> <span data-ttu-id="9092d-123">Gibt den Satz von .NET-Typen an, der die Bedingung auslöst.</span><span class="sxs-lookup"><span data-stu-id="9092d-123">Specifies the set of .NET types that triggers the condition.</span></span>|
|[<span data-ttu-id="9092d-124">Element „TypeName“ für SelectionCondition für Controls für Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="9092d-124">TypeName Element for SelectionCondition for Controls for Configuration (Format)</span></span>](./typename-element-for-selectioncondition-for-controls-for-configuration-format.md)|<span data-ttu-id="9092d-125">Optionales Element.</span><span class="sxs-lookup"><span data-stu-id="9092d-125">Optional element.</span></span><br /><br /> <span data-ttu-id="9092d-126">Gibt einen .NET-Typ an, der die Bedingung auslöst.</span><span class="sxs-lookup"><span data-stu-id="9092d-126">Specifies a .NET type that triggers the condition.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="9092d-127">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="9092d-127">Parent Elements</span></span>

|<span data-ttu-id="9092d-128">Element</span><span class="sxs-lookup"><span data-stu-id="9092d-128">Element</span></span>|<span data-ttu-id="9092d-129">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9092d-129">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="9092d-130">Element „EntrySelectedBy“ für CustomEntry für Controls für Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="9092d-130">EntrySelectedBy Element for CustomEntry for Controls for Configuration (Format)</span></span>](./entryselectedby-element-for-customentry-for-controls-for-configuration-format.md)|<span data-ttu-id="9092d-131">Definiert die .NET-Typen, die diesen Eintrag der allgemeinen Steuerelement Definition verwenden.</span><span class="sxs-lookup"><span data-stu-id="9092d-131">Defines the .NET types that use this entry of the common control definition.</span></span>|

## <a name="remarks"></a><span data-ttu-id="9092d-132">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="9092d-132">Remarks</span></span>

<span data-ttu-id="9092d-133">Die folgenden Richtlinien müssen befolgt werden, wenn eine Auswahlbedingung definiert wird:</span><span class="sxs-lookup"><span data-stu-id="9092d-133">The following guidelines must be followed when defining a selection condition:</span></span>

- <span data-ttu-id="9092d-134">Die Auswahlbedingung muss mindestens einen Eigenschaften Namen oder einen Skriptblock angeben, kann jedoch nicht beides angeben.</span><span class="sxs-lookup"><span data-stu-id="9092d-134">The selection condition must specify a least one property name or a script block, but cannot specify both.</span></span>

- <span data-ttu-id="9092d-135">Die Auswahlbedingung kann eine beliebige Anzahl von .NET-Typen oder-Auswahl Sätzen angeben, kann jedoch nicht beides angeben.</span><span class="sxs-lookup"><span data-stu-id="9092d-135">The selection condition can specify any number of .NET types or selection sets, but cannot specify both.</span></span>

<span data-ttu-id="9092d-136">Weitere Informationen zur Verwendung von Auswahl Bedingungen finden Sie unter [Definieren von Bedingungen für die Anzeige von Daten](./defining-conditions-for-displaying-data.md).</span><span class="sxs-lookup"><span data-stu-id="9092d-136">For more information about how selection conditions can be used, see [Defining Conditions for when Data is Displayed](./defining-conditions-for-displaying-data.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="9092d-137">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="9092d-137">See Also</span></span>

[<span data-ttu-id="9092d-138">Element „PropertyName“ für SelectionCondition für Controls für Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="9092d-138">PropertyName Element for SelectionCondition for Controls for Configuration (Format)</span></span>](./propertyname-element-for-selectioncondition-for-controls-for-configuration-format.md)

[<span data-ttu-id="9092d-139">Element „ScriptBlock“ für SelectionCondition für Controls für Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="9092d-139">ScriptBlock Element for SelectionCondition for Controls for Configuration (Format)</span></span>](./scriptblock-element-for-selectioncondition-for-controls-for-configuration-format.md)

[<span data-ttu-id="9092d-140">Element „SelectionSetName“ für SelectionCondition für Controls für Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="9092d-140">SelectionSetName Element for SelectionCondition for Controls for Configuration (Format)</span></span>](./selectionsetname-element-for-selectioncondition-for-controls-for-configuration-format.md)

[<span data-ttu-id="9092d-141">Element „TypeName“ für SelectionCondition für Controls für Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="9092d-141">TypeName Element for SelectionCondition for Controls for Configuration (Format)</span></span>](./typename-element-for-selectioncondition-for-controls-for-configuration-format.md)

[<span data-ttu-id="9092d-142">Element „EntrySelectedBy“ für CustomEntry für Controls für Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="9092d-142">EntrySelectedBy Element for CustomEntry for Controls for Configuration (Format)</span></span>](./entryselectedby-element-for-customentry-for-controls-for-configuration-format.md)

[<span data-ttu-id="9092d-143">Schreiben einer Windows PowerShell-Formatierungs-und-Typen Datei</span><span class="sxs-lookup"><span data-stu-id="9092d-143">Writing a Windows PowerShell Formatting and Types File</span></span>](./writing-a-powershell-formatting-file.md)
