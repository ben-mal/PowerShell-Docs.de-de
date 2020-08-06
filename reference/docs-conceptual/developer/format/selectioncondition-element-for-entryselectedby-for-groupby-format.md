---
title: Selectioncondition-Element für entryselectedby für GroupBy (Format) | Microsoft-Dokumentation
ms.date: 09/13/2016
ms.openlocfilehash: 0930d8076c314c12cac6cdfa2b33716b7efeb6a9
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2020
ms.locfileid: "87772840"
---
# <a name="selectioncondition-element-for-entryselectedby-for-groupby-format"></a><span data-ttu-id="41faa-102">Element „SelectionCondition“ für EntrySelectedBy für GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="41faa-102">SelectionCondition Element for EntrySelectedBy for GroupBy (Format)</span></span>

<span data-ttu-id="41faa-103">Definiert eine Bedingung, die vorhanden sein muss, damit eine Steuerelement Definition verwendet werden muss.</span><span class="sxs-lookup"><span data-stu-id="41faa-103">Defines a condition that must exist for a control definition to be used.</span></span> <span data-ttu-id="41faa-104">Dieses Element wird verwendet, wenn definiert wird, wie eine neue Gruppe von Objekten angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="41faa-104">This element is used when defining how a new group of objects is displayed.</span></span>

<span data-ttu-id="41faa-105">Configuration-Element (Format) viewdefinitions-Element (Format) Ansichts Element (Format) GroupBy-Element für View (Format) CustomControl-Element für GroupBy (Format) customentries-Element für CustomControl für GroupBy (Format) customentry-Element für CustomControl für GroupBy (Format) entryselectedby-Element für customentry für GroupBy (Format) selectioncondition-Element für entryselectedby für GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="41faa-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) GroupBy Element for View (Format) CustomControl Element for GroupBy (Format) CustomEntries Element for CustomControl for GroupBy (Format) CustomEntry Element for CustomControl for GroupBy (Format) EntrySelectedBy Element for CustomEntry for GroupBy (Format) SelectionCondition Element for EntrySelectedBy for GroupBy (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="41faa-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="41faa-106">Syntax</span></span>

```xml
<SelectionCondition>
  <TypeName>Nameof.NetType</TypeName>
  <SelectionSetName>NameofSelectionSet</SelectionSetName>
  <PropertyName>.NetTypeProperty</PropertyName>
  <ScriptBlock>ScriptToEvaluate</ScriptBlock>
</SelectionCondition>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="41faa-107">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="41faa-107">Attributes and Elements</span></span>

<span data-ttu-id="41faa-108">In den folgenden Abschnitten werden Attribute, untergeordnete Elemente und das übergeordnete Element des- `SelectionCondition` Elements beschrieben.</span><span class="sxs-lookup"><span data-stu-id="41faa-108">The following sections describe attributes, child elements, and the parent element of the `SelectionCondition` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="41faa-109">Attribute</span><span class="sxs-lookup"><span data-stu-id="41faa-109">Attributes</span></span>

<span data-ttu-id="41faa-110">Keine</span><span class="sxs-lookup"><span data-stu-id="41faa-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="41faa-111">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="41faa-111">Child Elements</span></span>

|<span data-ttu-id="41faa-112">Element</span><span class="sxs-lookup"><span data-stu-id="41faa-112">Element</span></span>|<span data-ttu-id="41faa-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="41faa-113">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="41faa-114">Element „PropertyName“ für SelectionCondition für GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="41faa-114">PropertyName Element for SelectionCondition for GroupBy (Format)</span></span>](./propertyname-element-for-selectioncondition-for-groupby-format.md)|<span data-ttu-id="41faa-115">Optionales Element.</span><span class="sxs-lookup"><span data-stu-id="41faa-115">Optional element.</span></span><br /><br /> <span data-ttu-id="41faa-116">Gibt eine .net-Eigenschaft an, die die Bedingung auslöst.</span><span class="sxs-lookup"><span data-stu-id="41faa-116">Specifies a .NET property that triggers the condition.</span></span>|
|[<span data-ttu-id="41faa-117">ScriptBlock-Element für selectioncondition für GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="41faa-117">ScriptBlock Element for SelectionCondition for GroupBy (Format)</span></span>](./scriptblock-element-for-selectioncondition-for-entryselectedby-for-groupby-format.md)|<span data-ttu-id="41faa-118">Optionales Element.</span><span class="sxs-lookup"><span data-stu-id="41faa-118">Optional element.</span></span><br /><br /> <span data-ttu-id="41faa-119">Gibt das Skript an, das die Bedingung auslöst.</span><span class="sxs-lookup"><span data-stu-id="41faa-119">Specifies the script that triggers the condition.</span></span>|
|[<span data-ttu-id="41faa-120">Element „SelectionSetName“ für SelectionCondition für GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="41faa-120">SelectionSetName Element for SelectionCondition for GroupBy (Format)</span></span>](./selectionsetname-element-for-selectioncondition-for-groupby-format.md)|<span data-ttu-id="41faa-121">Optionales Element.</span><span class="sxs-lookup"><span data-stu-id="41faa-121">Optional element.</span></span><br /><br /> <span data-ttu-id="41faa-122">Gibt den Satz von .NET-Typen an, der die Bedingung auslöst.</span><span class="sxs-lookup"><span data-stu-id="41faa-122">Specifies the set of .NET types that triggers the condition.</span></span>|
|[<span data-ttu-id="41faa-123">Typname-Element für selectioncondition für GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="41faa-123">TypeName Element for SelectionCondition for GroupBy  (Format)</span></span>](./typename-element-for-selectioncondition-for-groupby-format.md)|<span data-ttu-id="41faa-124">Optionales Element.</span><span class="sxs-lookup"><span data-stu-id="41faa-124">Optional element.</span></span><br /><br /> <span data-ttu-id="41faa-125">Gibt einen .NET-Typ an, der die Bedingung auslöst.</span><span class="sxs-lookup"><span data-stu-id="41faa-125">Specifies a .NET type that triggers the condition.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="41faa-126">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="41faa-126">Parent Elements</span></span>

|<span data-ttu-id="41faa-127">Element</span><span class="sxs-lookup"><span data-stu-id="41faa-127">Element</span></span>|<span data-ttu-id="41faa-128">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="41faa-128">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="41faa-129">Element „EntrySelectedBy“ für CustomEntry für GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="41faa-129">EntrySelectedBy Element for CustomEntry for GroupBy (Format)</span></span>](./entryselectedby-element-for-customentry-for-groupby-format.md)|<span data-ttu-id="41faa-130">Definiert die .NET-Typen, die diese Steuerelement Definition verwenden, oder die Bedingung, die vorhanden sein muss, damit diese Definition verwendet werden muss.</span><span class="sxs-lookup"><span data-stu-id="41faa-130">Defines the .NET types that use this control definition or the condition that must exist for this definition to be used.</span></span>|

## <a name="remarks"></a><span data-ttu-id="41faa-131">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="41faa-131">Remarks</span></span>

<span data-ttu-id="41faa-132">Wenn Sie eine Auswahlbedingung definieren, gelten die folgenden Anforderungen:</span><span class="sxs-lookup"><span data-stu-id="41faa-132">When you are defining a selection condition, the following requirements apply:</span></span>

- <span data-ttu-id="41faa-133">Die Auswahlbedingung muss mindestens einen Eigenschaften Namen oder einen Skriptblock angeben, kann jedoch nicht beides angeben.</span><span class="sxs-lookup"><span data-stu-id="41faa-133">The selection condition must specify a least one property name or a script block, but cannot specify both.</span></span>

- <span data-ttu-id="41faa-134">Die Auswahlbedingung kann eine beliebige Anzahl von .NET-Typen oder-Auswahl Sätzen angeben, kann jedoch nicht beides angeben.</span><span class="sxs-lookup"><span data-stu-id="41faa-134">The selection condition can specify any number of .NET types or selection sets, but cannot specify both.</span></span>

<span data-ttu-id="41faa-135">Weitere Informationen zum Verwenden von Auswahl Bedingungen finden Sie unter [Definieren von Bedingungen für die Anzeige von Daten](./defining-conditions-for-displaying-data.md).</span><span class="sxs-lookup"><span data-stu-id="41faa-135">For more information about how to use selection conditions, see [Defining Conditions for when Data is Displayed](./defining-conditions-for-displaying-data.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="41faa-136">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="41faa-136">See Also</span></span>

[<span data-ttu-id="41faa-137">Element „PropertyName“ für SelectionCondition für CustomControl für View (Format)</span><span class="sxs-lookup"><span data-stu-id="41faa-137">PropertyName Element for SelectionCondition for CustomControl for View (Format)</span></span>](./propertyname-element-for-selectioncondition-for-customcontrol-for-view-format.md)

[<span data-ttu-id="41faa-138">Element „ScriptBlock“ für SelectionCondition für CustomControl für View (Format)</span><span class="sxs-lookup"><span data-stu-id="41faa-138">ScriptBlock Element for SelectionCondition for CustomControl for View (Format)</span></span>](./scriptblock-element-for-selectioncondition-for-customcontrol-for-view-format.md)

[<span data-ttu-id="41faa-139">Selectionsetname-Element für selectioncondition für benutzerdefiniertes Steuer Element für Ansicht (Format)</span><span class="sxs-lookup"><span data-stu-id="41faa-139">SelectionSetName Element for SelectionCondition for Custom Control for View (Format)</span></span>](./selectionsetname-element-for-selectioncondition-for-customcontrol-for-view-format.md)

[<span data-ttu-id="41faa-140">Typname-Element für selectioncondition für GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="41faa-140">TypeName Element for SelectionCondition for GroupBy  (Format)</span></span>](./typename-element-for-selectioncondition-for-groupby-format.md)

[<span data-ttu-id="41faa-141">Element „EntrySelectedBy“ für CustomEntry für GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="41faa-141">EntrySelectedBy Element for CustomEntry for GroupBy (Format)</span></span>](./entryselectedby-element-for-customentry-for-groupby-format.md)

[<span data-ttu-id="41faa-142">Schreiben einer PowerShell-Formatierungsdatei</span><span class="sxs-lookup"><span data-stu-id="41faa-142">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
