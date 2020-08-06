---
title: Selectioncondition-Element für entryselectedby für Steuerelemente für Ansicht (Format) | Microsoft-Dokumentation
ms.date: 09/13/2016
ms.openlocfilehash: 1c14b2638249bdbfe25f7a96e917d66ea10ed239
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2020
ms.locfileid: "87787579"
---
# <a name="selectioncondition-element-for-entryselectedby-for-controls-for-view-format"></a><span data-ttu-id="434da-102">Element „SelectionCondition“ für EntrySelectedBy für Controls für View (Format)</span><span class="sxs-lookup"><span data-stu-id="434da-102">SelectionCondition Element for EntrySelectedBy for Controls for View (Format)</span></span>

<span data-ttu-id="434da-103">Definiert eine Bedingung, die vorhanden sein muss, damit die Steuerelement Definition verwendet werden muss.</span><span class="sxs-lookup"><span data-stu-id="434da-103">Defines a condition that must exist for the control definition to be used.</span></span> <span data-ttu-id="434da-104">Dieses Element wird beim Definieren von Steuerelementen verwendet, die von einer Ansicht verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="434da-104">This element is used when defining controls that can be used by a view.</span></span>

<span data-ttu-id="434da-105">Konfigurationselement (Format) viewdefinitions-Element (Format) Ansichts Element (Format) steuert Element (Format) Steuerelement für Steuerelemente für Ansicht (Format) CustomControl-Element für Steuerelemente für das View (Format) customentries-Element für CustomControl für Steuerelemente View (Format) customentry-Element für customentries für Steuerelemente für das View (Format) entryselectedby-Element für customentry für Steuerelemente für View (Format) selectioncondition-Element für entryselectedby für Steuerelemente für View (Format)</span><span class="sxs-lookup"><span data-stu-id="434da-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) Controls Element (Format) Control Element for Controls for View (Format) CustomControl Element for Control for Controls for View (Format) CustomEntries Element for CustomControl for Controls for View (Format) CustomEntry Element for CustomEntries for Controls for View (Format) EntrySelectedBy Element for CustomEntry for Controls for View (Format) SelectionCondition Element for EntrySelectedBy for Controls for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="434da-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="434da-106">Syntax</span></span>

```xml
<SelectionCondition>
  <TypeName>Nameof.NetType</TypeName>
  <SelectionSetName>NameofSelectionSet</SelectionSetName>
  <PropertyName>.NetTypeProperty</PropertyName>
  <ScriptBlock>ScriptToEvaluate</ScriptBlock>
</SelectionCondition>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="434da-107">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="434da-107">Attributes and Elements</span></span>

<span data-ttu-id="434da-108">In den folgenden Abschnitten werden Attribute, untergeordnete Elemente und das übergeordnete Element des- `SelectionCondition` Elements beschrieben.</span><span class="sxs-lookup"><span data-stu-id="434da-108">The following sections describe attributes, child elements, and the parent element of the `SelectionCondition` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="434da-109">Attribute</span><span class="sxs-lookup"><span data-stu-id="434da-109">Attributes</span></span>

<span data-ttu-id="434da-110">Keine</span><span class="sxs-lookup"><span data-stu-id="434da-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="434da-111">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="434da-111">Child Elements</span></span>

|<span data-ttu-id="434da-112">Element</span><span class="sxs-lookup"><span data-stu-id="434da-112">Element</span></span>|<span data-ttu-id="434da-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="434da-113">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="434da-114">Element „PropertyName“ für SelectionCondition für Controls für View (Format)</span><span class="sxs-lookup"><span data-stu-id="434da-114">PropertyName Element for SelectionCondition for Controls for View (Format)</span></span>](./propertyname-element-for-selectioncondition-for-controls-for-view-format.md)|<span data-ttu-id="434da-115">Optionales Element.</span><span class="sxs-lookup"><span data-stu-id="434da-115">Optional element.</span></span><br /><br /> <span data-ttu-id="434da-116">Gibt eine .net-Eigenschaft an, die die Bedingung auslöst.</span><span class="sxs-lookup"><span data-stu-id="434da-116">Specifies a .NET property that triggers the condition.</span></span>|
|[<span data-ttu-id="434da-117">Element „ScriptBlock“ für SelectionCondition für Controls für View (Format)</span><span class="sxs-lookup"><span data-stu-id="434da-117">ScriptBlock Element for SelectionCondition for Controls for View (Format)</span></span>](./scriptblock-element-for-selectioncondition-for-controls-for-view-format.md)|<span data-ttu-id="434da-118">Optionales Element.</span><span class="sxs-lookup"><span data-stu-id="434da-118">Optional element.</span></span><br /><br /> <span data-ttu-id="434da-119">Gibt das Skript an, das die Bedingung auslöst.</span><span class="sxs-lookup"><span data-stu-id="434da-119">Specifies the script that triggers the condition.</span></span>|
|[<span data-ttu-id="434da-120">Element „SelectionSetName“ für SelectionCondition für Controls für View (Format)</span><span class="sxs-lookup"><span data-stu-id="434da-120">SelectionSetName Element for SelectionCondition for Controls for View (Format)</span></span>](./selectionsetname-element-for-selectioncondition-for-controls-for-view-format.md)|<span data-ttu-id="434da-121">Optionales Element.</span><span class="sxs-lookup"><span data-stu-id="434da-121">Optional element.</span></span><br /><br /> <span data-ttu-id="434da-122">Gibt den Satz von .NET-Typen an, der die Bedingung auslöst.</span><span class="sxs-lookup"><span data-stu-id="434da-122">Specifies the set of .NET types that triggers the condition.</span></span>|
|[<span data-ttu-id="434da-123">Element „TypeName“ für SelectionCondition für Controls für View (Format)</span><span class="sxs-lookup"><span data-stu-id="434da-123">TypeName Element for SelectionCondition for Controls for View (Format)</span></span>](./typename-element-for-selectioncondition-for-controls-for-view-format.md)|<span data-ttu-id="434da-124">Optionales Element.</span><span class="sxs-lookup"><span data-stu-id="434da-124">Optional element.</span></span><br /><br /> <span data-ttu-id="434da-125">Gibt einen .NET-Typ an, der die Bedingung auslöst.</span><span class="sxs-lookup"><span data-stu-id="434da-125">Specifies a .NET type that triggers the condition.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="434da-126">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="434da-126">Parent Elements</span></span>

|<span data-ttu-id="434da-127">Element</span><span class="sxs-lookup"><span data-stu-id="434da-127">Element</span></span>|<span data-ttu-id="434da-128">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="434da-128">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="434da-129">Element „EntrySelectedBy“ für CustomEntry für Controls für View (Format)</span><span class="sxs-lookup"><span data-stu-id="434da-129">EntrySelectedBy Element for CustomEntry for Controls for View (Format)</span></span>](./entryselectedby-element-for-customentry-for-controls-for-view-format.md)|<span data-ttu-id="434da-130">Definiert die .NET-Typen, die diese Steuerelement Definition verwenden, oder die Bedingung, die vorhanden sein muss, damit diese Definition verwendet werden muss.</span><span class="sxs-lookup"><span data-stu-id="434da-130">Defines the .NET types that use this control definition or the condition that must exist for this definition to be used.</span></span>|

## <a name="remarks"></a><span data-ttu-id="434da-131">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="434da-131">Remarks</span></span>

<span data-ttu-id="434da-132">Wenn Sie eine Auswahlbedingung definieren, gelten die folgenden Anforderungen:</span><span class="sxs-lookup"><span data-stu-id="434da-132">When you are defining a selection condition, the following requirements apply:</span></span>

- <span data-ttu-id="434da-133">Die Auswahlbedingung muss mindestens einen Eigenschaften Namen oder einen Skriptblock angeben, kann jedoch nicht beides angeben.</span><span class="sxs-lookup"><span data-stu-id="434da-133">The selection condition must specify a least one property name or a script block, but cannot specify both.</span></span>

- <span data-ttu-id="434da-134">Die Auswahlbedingung kann eine beliebige Anzahl von .NET-Typen oder-Auswahl Sätzen angeben, kann jedoch nicht beides angeben.</span><span class="sxs-lookup"><span data-stu-id="434da-134">The selection condition can specify any number of .NET types or selection sets, but cannot specify both.</span></span>

<span data-ttu-id="434da-135">Weitere Informationen zum Verwenden von Auswahl Bedingungen finden Sie unter [Definieren von Bedingungen für die Anzeige von Daten](./defining-conditions-for-displaying-data.md).</span><span class="sxs-lookup"><span data-stu-id="434da-135">For more information about how to use selection conditions, see [Defining Conditions for when Data is Displayed](./defining-conditions-for-displaying-data.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="434da-136">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="434da-136">See Also</span></span>

[<span data-ttu-id="434da-137">Element „PropertyName“ für SelectionCondition für Controls für View (Format)</span><span class="sxs-lookup"><span data-stu-id="434da-137">PropertyName Element for SelectionCondition for Controls for View (Format)</span></span>](./propertyname-element-for-selectioncondition-for-controls-for-view-format.md)

[<span data-ttu-id="434da-138">Element „ScriptBlock“ für SelectionCondition für Controls für View (Format)</span><span class="sxs-lookup"><span data-stu-id="434da-138">ScriptBlock Element for SelectionCondition for Controls for View (Format)</span></span>](./scriptblock-element-for-selectioncondition-for-controls-for-view-format.md)

[<span data-ttu-id="434da-139">Element „SelectionSetName“ für SelectionCondition für Controls für View (Format)</span><span class="sxs-lookup"><span data-stu-id="434da-139">SelectionSetName Element for SelectionCondition for Controls for View (Format)</span></span>](./selectionsetname-element-for-selectioncondition-for-controls-for-view-format.md)

[<span data-ttu-id="434da-140">Element „TypeName“ für SelectionCondition für Controls für View (Format)</span><span class="sxs-lookup"><span data-stu-id="434da-140">TypeName Element for SelectionCondition for Controls for View (Format)</span></span>](./typename-element-for-selectioncondition-for-controls-for-view-format.md)

[<span data-ttu-id="434da-141">Element „EntrySelectedBy“ für CustomEntry für Controls für View (Format)</span><span class="sxs-lookup"><span data-stu-id="434da-141">EntrySelectedBy Element for CustomEntry for Controls for View (Format)</span></span>](./entryselectedby-element-for-customentry-for-controls-for-view-format.md)

[<span data-ttu-id="434da-142">Schreiben einer PowerShell-Formatierungsdatei</span><span class="sxs-lookup"><span data-stu-id="434da-142">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
