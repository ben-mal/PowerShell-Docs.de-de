---
ms.date: 09/13/2016
ms.topic: reference
title: Element „EntrySelectedBy“ für CustomEntry für Controls für View (Format)
description: Element „EntrySelectedBy“ für CustomEntry für Controls für View (Format)
ms.openlocfilehash: 29b0574a95d81962fb3f72a526f89273baeea647
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92660267"
---
# <a name="entryselectedby-element-for-customentry-for-controls-for-view-format"></a><span data-ttu-id="8c546-103">Element „EntrySelectedBy“ für CustomEntry für Controls für View (Format)</span><span class="sxs-lookup"><span data-stu-id="8c546-103">EntrySelectedBy Element for CustomEntry for Controls for View (Format)</span></span>

<span data-ttu-id="8c546-104">Definiert die .NET-Typen, die diese Steuerelement Definition verwenden, oder die Bedingung, die vorhanden sein muss, damit diese Definition verwendet werden muss.</span><span class="sxs-lookup"><span data-stu-id="8c546-104">Defines the .NET types that use this control definition or the condition that must exist for this definition to be used.</span></span> <span data-ttu-id="8c546-105">Dieses Element wird beim Definieren von Steuerelementen verwendet, die von einer Ansicht verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="8c546-105">This element is used when defining controls that can be used by a view.</span></span>

<span data-ttu-id="8c546-106">Konfigurationselement (Format) viewdefinitions-Element (Format) Ansichts Element (Format) Steuerelemente Element (Format) Steuerelement für Steuerelemente für Ansicht (Format) CustomControl-Element für Steuerelemente für Ansicht (Format) customentries-Element für CustomControl für Steuerelemente für das View (Format) customentry-Element für customentries für Steuerelemente für das View (Format) entryselectedby-Element für customentry für Steuerelemente für View (Format)</span><span class="sxs-lookup"><span data-stu-id="8c546-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) Controls Element (Format) Control Element for Controls for View (Format) CustomControl Element for Control for Controls for View (Format) CustomEntries Element for CustomControl for Controls for View (Format) CustomEntry Element for CustomEntries for Controls for View (Format) EntrySelectedBy Element for CustomEntry for Controls for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="8c546-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="8c546-107">Syntax</span></span>

```xml
<EntrySelectedBy>
  <TypeName>Nameof.NetType</TypeName>
  <SelectionSetName>NameofSelectionSet</SelectionSetName>
  <SelectionCondition>...</SelectionCondition>
</EntrySelectedBy>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="8c546-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="8c546-108">Attributes and Elements</span></span>

<span data-ttu-id="8c546-109">In den folgenden Abschnitten werden Attribute, untergeordnete Elemente und das übergeordnete Element des- `EntrySelectedBy` Elements beschrieben.</span><span class="sxs-lookup"><span data-stu-id="8c546-109">The following sections describe attributes, child elements, and parent element of the `EntrySelectedBy` element.</span></span> <span data-ttu-id="8c546-110">Sie müssen mindestens einen Typ, einen Auswahl Satz oder eine Auswahlbedingung für eine Definition angeben.</span><span class="sxs-lookup"><span data-stu-id="8c546-110">You must specify at least one type, selection set, or selection condition for a definition.</span></span> <span data-ttu-id="8c546-111">Es gibt keine maximale Beschränkung für die Anzahl der untergeordneten Elemente, die Sie verwenden können.</span><span class="sxs-lookup"><span data-stu-id="8c546-111">There is no maximum limit to the number of child elements that you can use.</span></span>

### <a name="attributes"></a><span data-ttu-id="8c546-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="8c546-112">Attributes</span></span>

<span data-ttu-id="8c546-113">Keine</span><span class="sxs-lookup"><span data-stu-id="8c546-113">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="8c546-114">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="8c546-114">Child Elements</span></span>

|<span data-ttu-id="8c546-115">Element</span><span class="sxs-lookup"><span data-stu-id="8c546-115">Element</span></span>|<span data-ttu-id="8c546-116">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="8c546-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="8c546-117">Element „SelectionCondition“ für EntrySelectedBy für Controls für View (Format)</span><span class="sxs-lookup"><span data-stu-id="8c546-117">SelectionCondition Element for EntrySelectedBy for Controls for View (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-controls-for-view-format.md)|<span data-ttu-id="8c546-118">Optionales Element.</span><span class="sxs-lookup"><span data-stu-id="8c546-118">Optional element.</span></span><br /><br /> <span data-ttu-id="8c546-119">Definiert die Bedingung, die vorhanden sein muss, damit diese Definition verwendet werden muss.</span><span class="sxs-lookup"><span data-stu-id="8c546-119">Defines the condition that must exist for this definition to be used.</span></span>|
|[<span data-ttu-id="8c546-120">Element „SelectionSetName“ für EntrySelectedBy für Controls für View (Format)</span><span class="sxs-lookup"><span data-stu-id="8c546-120">SelectionSetName Element for EntrySelectedBy for Controls for View (Format)</span></span>](./selectionsetname-element-for-entryselectedby-for-controls-for-view-format.md)|<span data-ttu-id="8c546-121">Optionales Element.</span><span class="sxs-lookup"><span data-stu-id="8c546-121">Optional element.</span></span><br /><br /> <span data-ttu-id="8c546-122">Gibt einen Satz von .NET-Typen an, die diese Definition des-Steuer Elements verwenden.</span><span class="sxs-lookup"><span data-stu-id="8c546-122">Specifies a set of .NET types that use this definition of the control.</span></span>|
|[<span data-ttu-id="8c546-123">Element „TypeName“ für EntrySelectedBy für Controls für View (Format)</span><span class="sxs-lookup"><span data-stu-id="8c546-123">TypeName Element for EntrySelectedBy for Controls for View (Format)</span></span>](./typename-element-for-entryselectedby-for-controls-for-view-format.md)|<span data-ttu-id="8c546-124">Optionales Element.</span><span class="sxs-lookup"><span data-stu-id="8c546-124">Optional element.</span></span><br /><br /> <span data-ttu-id="8c546-125">Gibt einen .NET-Typ an, der diese Definition des-Steuer Elements verwendet.</span><span class="sxs-lookup"><span data-stu-id="8c546-125">Specifies a .NET type that uses this definition of the control.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="8c546-126">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="8c546-126">Parent Elements</span></span>

|<span data-ttu-id="8c546-127">Element</span><span class="sxs-lookup"><span data-stu-id="8c546-127">Element</span></span>|<span data-ttu-id="8c546-128">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="8c546-128">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="8c546-129">Element „CustomEntry“ für CustomEntries für Controls für View (Format)</span><span class="sxs-lookup"><span data-stu-id="8c546-129">CustomEntry Element for CustomEntries for Controls for View (Format)</span></span>](./customentry-element-for-customentries-for-controls-for-view-format.md)|<span data-ttu-id="8c546-130">Stellt eine Definition des-Steuer Elements bereit.</span><span class="sxs-lookup"><span data-stu-id="8c546-130">Provides a definition of the control.</span></span>|

## <a name="remarks"></a><span data-ttu-id="8c546-131">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="8c546-131">Remarks</span></span>

<span data-ttu-id="8c546-132">Auswahl Bedingungen werden verwendet, um eine Bedingung zu definieren, die für die zu verwendende Definition vorhanden sein muss, z. b. Wenn ein Objekt eine bestimmte Eigenschaft hat oder wenn ein bestimmter Eigenschafts Wert oder ein Skript als ausgewertet wird `true` .</span><span class="sxs-lookup"><span data-stu-id="8c546-132">Selection conditions are used to define a condition that must exist for the definition to be used, such as when an object has a specific property or when a specific property value or script evaluates to `true`.</span></span> <span data-ttu-id="8c546-133">Weitere Informationen zu Auswahl Bedingungen finden Sie unter [Definieren von Bedingungen für die Verwendung eines Ansichts Eintrags oder eines Elements](./defining-conditions-for-displaying-data.md).</span><span class="sxs-lookup"><span data-stu-id="8c546-133">For more information about selection conditions, see [Defining Conditions for when a View Entry or Item is Used](./defining-conditions-for-displaying-data.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="8c546-134">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="8c546-134">See Also</span></span>

[<span data-ttu-id="8c546-135">Element „CustomEntry“ für CustomEntries für Controls für View (Format)</span><span class="sxs-lookup"><span data-stu-id="8c546-135">CustomEntry Element for CustomEntries for Controls for View (Format)</span></span>](./customentry-element-for-customentries-for-controls-for-view-format.md)

[<span data-ttu-id="8c546-136">Schreiben einer PowerShell-Formatierungsdatei</span><span class="sxs-lookup"><span data-stu-id="8c546-136">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
