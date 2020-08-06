---
title: Selectioncondition-Element für entryselectedby für CustomControl (Format) | Microsoft-Dokumentation
ms.date: 09/13/2016
ms.openlocfilehash: 52858dba5c7a5222b5410835f3374546ce8b88a2
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2020
ms.locfileid: "87785352"
---
# <a name="selectioncondition-element-for-entryselectedby-for-customcontrol-format"></a><span data-ttu-id="9234b-102">Element „SelectionCondition“ für EntrySelectedBy für CustomControl (Format)</span><span class="sxs-lookup"><span data-stu-id="9234b-102">SelectionCondition Element for EntrySelectedBy for CustomControl (Format)</span></span>

<span data-ttu-id="9234b-103">Definiert eine Bedingung, die vorhanden sein muss, damit eine Steuerelement Definition verwendet werden muss.</span><span class="sxs-lookup"><span data-stu-id="9234b-103">Defines a condition that must exist for a control definition to be used.</span></span> <span data-ttu-id="9234b-104">Dieses Element wird beim Definieren einer benutzerdefinierten Steuerelement Ansicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="9234b-104">This element is used when defining a custom control view.</span></span>

<span data-ttu-id="9234b-105">Konfigurationselement (Format) viewdefinitions-Element (Format) View-Element (Format) CustomControl-Element für View (Format) customentries-Element für CustomControl for View (Format) customentry-Element für customentries für CustomControl for View (Format) customItem-Element für customentry für CustomControl für das View (Format) entryselectedby-Element für customentry für CustomControl für View (Format) selectioncondition-Element für entryselectedby für CustomControl for View (Format)</span><span class="sxs-lookup"><span data-stu-id="9234b-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) CustomControl Element for View (Format) CustomEntries Element for CustomControl for View (Format) CustomEntry Element for CustomEntries for CustomControl for View (Format) CustomItem Element for CustomEntry for CustomControl for View (Format) EntrySelectedBy Element for CustomEntry for CustomControl for View (Format) SelectionCondition Element for EntrySelectedBy for CustomControl for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="9234b-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="9234b-106">Syntax</span></span>

```xml
<SelectionCondition>
  <TypeName>Nameof.NetType</TypeName>
  <SelectionSetName>NameofSelectionSet</SelectionSetName>
  <PropertyName>.NetTypeProperty</PropertyName>
  <ScriptBlock>ScriptToEvaluate</ScriptBlock>
</SelectionCondition>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="9234b-107">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="9234b-107">Attributes and Elements</span></span>

<span data-ttu-id="9234b-108">In den folgenden Abschnitten werden Attribute, untergeordnete Elemente und das übergeordnete Element des- `SelectionCondition` Elements beschrieben.</span><span class="sxs-lookup"><span data-stu-id="9234b-108">The following sections describe attributes, child elements, and the parent element of the `SelectionCondition` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="9234b-109">Attribute</span><span class="sxs-lookup"><span data-stu-id="9234b-109">Attributes</span></span>

<span data-ttu-id="9234b-110">Keine</span><span class="sxs-lookup"><span data-stu-id="9234b-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="9234b-111">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="9234b-111">Child Elements</span></span>

|<span data-ttu-id="9234b-112">Element</span><span class="sxs-lookup"><span data-stu-id="9234b-112">Element</span></span>|<span data-ttu-id="9234b-113">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="9234b-113">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="9234b-114">Element „PropertyName“ für SelectionCondition für CustomControl für View (Format)</span><span class="sxs-lookup"><span data-stu-id="9234b-114">PropertyName Element for SelectionCondition for CustomControl for View (Format)</span></span>](./propertyname-element-for-selectioncondition-for-customcontrol-for-view-format.md)|<span data-ttu-id="9234b-115">Optionales Element.</span><span class="sxs-lookup"><span data-stu-id="9234b-115">Optional element.</span></span><br /><br /> <span data-ttu-id="9234b-116">Gibt eine .net-Eigenschaft an, die die Bedingung auslöst.</span><span class="sxs-lookup"><span data-stu-id="9234b-116">Specifies a .NET property that triggers the condition.</span></span>|
|[<span data-ttu-id="9234b-117">Element „ScriptBlock“ für SelectionCondition für CustomControl für View (Format)</span><span class="sxs-lookup"><span data-stu-id="9234b-117">ScriptBlock Element for SelectionCondition for CustomControl for View (Format)</span></span>](./scriptblock-element-for-selectioncondition-for-customcontrol-for-view-format.md)|<span data-ttu-id="9234b-118">Optionales Element.</span><span class="sxs-lookup"><span data-stu-id="9234b-118">Optional element.</span></span><br /><br /> <span data-ttu-id="9234b-119">Gibt das Skript an, das die Bedingung auslöst.</span><span class="sxs-lookup"><span data-stu-id="9234b-119">Specifies the script that triggers the condition.</span></span>|
|[<span data-ttu-id="9234b-120">Selectionsetname-Element für selectioncondition für benutzerdefiniertes Steuer Element für Ansicht (Format)</span><span class="sxs-lookup"><span data-stu-id="9234b-120">SelectionSetName Element for SelectionCondition for Custom Control for View (Format)</span></span>](./selectionsetname-element-for-selectioncondition-for-customcontrol-for-view-format.md)|<span data-ttu-id="9234b-121">Optionales Element.</span><span class="sxs-lookup"><span data-stu-id="9234b-121">Optional element.</span></span><br /><br /> <span data-ttu-id="9234b-122">Gibt den Satz von .NET-Typen an, der die Bedingung auslöst.</span><span class="sxs-lookup"><span data-stu-id="9234b-122">Specifies the set of .NET types that triggers the condition.</span></span>|
|[<span data-ttu-id="9234b-123">Element „TypeName“ für SelectionCondition für CustomControl für View (Format)</span><span class="sxs-lookup"><span data-stu-id="9234b-123">TypeName Element for SelectionCondition for CustomControl for View  (Format)</span></span>](./typename-element-for-selectioncondition-for-customcontrol-for-view-format.md)|<span data-ttu-id="9234b-124">Optionales Element.</span><span class="sxs-lookup"><span data-stu-id="9234b-124">Optional element.</span></span><br /><br /> <span data-ttu-id="9234b-125">Gibt einen .NET-Typ an, der die Bedingung auslöst.</span><span class="sxs-lookup"><span data-stu-id="9234b-125">Specifies a .NET type that triggers the condition.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="9234b-126">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="9234b-126">Parent Elements</span></span>

|<span data-ttu-id="9234b-127">Element</span><span class="sxs-lookup"><span data-stu-id="9234b-127">Element</span></span>|<span data-ttu-id="9234b-128">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="9234b-128">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="9234b-129">Element „EntrySelectedBy“ für CustomEntry für CustomControl für View (Format)</span><span class="sxs-lookup"><span data-stu-id="9234b-129">EntrySelectedBy Element for CustomEntry for CustomControl for View (Format)</span></span>](./entryselectedby-element-for-customentry-for-customcontrol-for-view-format.md)|<span data-ttu-id="9234b-130">Definiert die .NET-Typen, die diese Steuerelement Definition verwenden, oder die Bedingung, die vorhanden sein muss, damit diese Definition verwendet werden muss.</span><span class="sxs-lookup"><span data-stu-id="9234b-130">Defines the .NET types that use this control definition or the condition that must exist for this definition to be used.</span></span>|

## <a name="remarks"></a><span data-ttu-id="9234b-131">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="9234b-131">Remarks</span></span>

<span data-ttu-id="9234b-132">Wenn Sie eine Auswahlbedingung definieren, gelten die folgenden Anforderungen:</span><span class="sxs-lookup"><span data-stu-id="9234b-132">When you are defining a selection condition, the following requirements apply:</span></span>

- <span data-ttu-id="9234b-133">Die Auswahlbedingung muss mindestens einen Eigenschaften Namen oder einen Skriptblock angeben, kann jedoch nicht beides angeben.</span><span class="sxs-lookup"><span data-stu-id="9234b-133">The selection condition must specify a least one property name or a script block, but cannot specify both.</span></span>

- <span data-ttu-id="9234b-134">Die Auswahlbedingung kann eine beliebige Anzahl von .NET-Typen oder-Auswahl Sätzen angeben, kann jedoch nicht beides angeben.</span><span class="sxs-lookup"><span data-stu-id="9234b-134">The selection condition can specify any number of .NET types or selection sets, but cannot specify both.</span></span>

<span data-ttu-id="9234b-135">Weitere Informationen zum Verwenden von Auswahl Bedingungen finden Sie unter [Definieren von Bedingungen für die Anzeige von Daten](./defining-conditions-for-displaying-data.md).</span><span class="sxs-lookup"><span data-stu-id="9234b-135">For more information about how to use selection conditions, see [Defining Conditions for when Data is Displayed](./defining-conditions-for-displaying-data.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="9234b-136">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="9234b-136">See Also</span></span>

[<span data-ttu-id="9234b-137">Element „PropertyName“ für SelectionCondition für CustomControl für View (Format)</span><span class="sxs-lookup"><span data-stu-id="9234b-137">PropertyName Element for SelectionCondition for CustomControl for View (Format)</span></span>](./propertyname-element-for-selectioncondition-for-customcontrol-for-view-format.md)

[<span data-ttu-id="9234b-138">Element „ScriptBlock“ für SelectionCondition für CustomControl für View (Format)</span><span class="sxs-lookup"><span data-stu-id="9234b-138">ScriptBlock Element for SelectionCondition for CustomControl for View (Format)</span></span>](./scriptblock-element-for-selectioncondition-for-customcontrol-for-view-format.md)

[<span data-ttu-id="9234b-139">Selectionsetname-Element für selectioncondition für benutzerdefiniertes Steuer Element für Ansicht (Format)</span><span class="sxs-lookup"><span data-stu-id="9234b-139">SelectionSetName Element for SelectionCondition for Custom Control for View (Format)</span></span>](./selectionsetname-element-for-selectioncondition-for-customcontrol-for-view-format.md)

[<span data-ttu-id="9234b-140">Element „TypeName“ für SelectionCondition für CustomControl für View (Format)</span><span class="sxs-lookup"><span data-stu-id="9234b-140">TypeName Element for SelectionCondition for CustomControl for View  (Format)</span></span>](./typename-element-for-selectioncondition-for-customcontrol-for-view-format.md)

[<span data-ttu-id="9234b-141">Element „EntrySelectedBy“ für CustomEntry für CustomControl für View (Format)</span><span class="sxs-lookup"><span data-stu-id="9234b-141">EntrySelectedBy Element for CustomEntry for CustomControl for View (Format)</span></span>](./entryselectedby-element-for-customentry-for-customcontrol-for-view-format.md)

[<span data-ttu-id="9234b-142">Schreiben einer PowerShell-Formatierungsdatei</span><span class="sxs-lookup"><span data-stu-id="9234b-142">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
