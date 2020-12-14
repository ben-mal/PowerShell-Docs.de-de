---
ms.date: 09/13/2016
ms.topic: reference
title: Element „PropertyName“ für SelectionCondition für EntrySelectedBy für WideEntry (Format)
description: Element „PropertyName“ für SelectionCondition für EntrySelectedBy für WideEntry (Format)
ms.openlocfilehash: bda34b0c1e97fb85536132bedcec3986072801b7
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92665701"
---
# <a name="propertyname-element-for-selectioncondition-for-entryselectedby-for-wideentry-format"></a><span data-ttu-id="a7276-103">Element „PropertyName“ für SelectionCondition für EntrySelectedBy für WideEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="a7276-103">PropertyName Element for SelectionCondition for EntrySelectedBy for WideEntry (Format)</span></span>

<span data-ttu-id="a7276-104">Gibt die .net-Eigenschaft an, die die Bedingung auslöst.</span><span class="sxs-lookup"><span data-stu-id="a7276-104">Specifies the .NET property that triggers the condition.</span></span> <span data-ttu-id="a7276-105">Wenn diese Eigenschaft vorhanden ist oder als ausgewertet wird `true` , wird die Bedingung erfüllt, und die Definition wird verwendet.</span><span class="sxs-lookup"><span data-stu-id="a7276-105">When this property is present or when it evaluates to `true`, the condition is met, and the definition is used.</span></span>

<span data-ttu-id="a7276-106">Configuration-Element (Format) viewdefinitions-Element (Format) Ansichts Element (Format) widecontrol-Element (Format) wideentries-Element (Format) wideentry-Element (Format) entryselectedby-Element für wideentry (Format) selectioncondition-Element für entryselectedby für wideentry (Format) propertyName-Element für selectioncondition für entryselectedby für wideentry (Format)</span><span class="sxs-lookup"><span data-stu-id="a7276-106">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) WideControl Element (Format) WideEntries Element (Format) WideEntry Element (Format) EntrySelectedBy Element for WideEntry (Format) SelectionCondition Element for EntrySelectedBy for WideEntry (Format) PropertyName Element for SelectionCondition for EntrySelectedBy for WideEntry (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="a7276-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="a7276-107">Syntax</span></span>

```xml
<PropertyName>.NetTypeProperty</PropertyName>
```

```csharp

```

## <a name="attributes-and-elements"></a><span data-ttu-id="a7276-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="a7276-108">Attributes and Elements</span></span>

<span data-ttu-id="a7276-109">In den folgenden Abschnitten werden Attribute, untergeordnete Elemente und das übergeordnete Element des- `PropertyName` Elements beschrieben.</span><span class="sxs-lookup"><span data-stu-id="a7276-109">The following sections describe attributes, child elements, and the parent element of the `PropertyName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="a7276-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="a7276-110">Attributes</span></span>

<span data-ttu-id="a7276-111">Keine</span><span class="sxs-lookup"><span data-stu-id="a7276-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="a7276-112">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="a7276-112">Child Elements</span></span>

<span data-ttu-id="a7276-113">Keine</span><span class="sxs-lookup"><span data-stu-id="a7276-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="a7276-114">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="a7276-114">Parent Elements</span></span>

|<span data-ttu-id="a7276-115">Element</span><span class="sxs-lookup"><span data-stu-id="a7276-115">Element</span></span>|<span data-ttu-id="a7276-116">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a7276-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="a7276-117">Selectioncondition-Element für entryselectedby für wideentry (Format)</span><span class="sxs-lookup"><span data-stu-id="a7276-117">SelectionCondition Element for EntrySelectedBy for WideEntry (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-widecontrol-format.md)|<span data-ttu-id="a7276-118">Definiert die Bedingung, die vorhanden sein muss, damit diese Definition verwendet werden muss.</span><span class="sxs-lookup"><span data-stu-id="a7276-118">Defines the condition that must exist for this definition to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="a7276-119">Textwert</span><span class="sxs-lookup"><span data-stu-id="a7276-119">Text Value</span></span>

<span data-ttu-id="a7276-120">Geben Sie den Namen der .net-Eigenschaft an.</span><span class="sxs-lookup"><span data-stu-id="a7276-120">Specify the .NET property name.</span></span>

## <a name="remarks"></a><span data-ttu-id="a7276-121">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="a7276-121">Remarks</span></span>

<span data-ttu-id="a7276-122">Die Auswahlbedingung muss mindestens einen Eigenschaften Namen oder ein auszuwertende Skript angeben, kann jedoch nicht beides angeben.</span><span class="sxs-lookup"><span data-stu-id="a7276-122">The selection condition must specify at least one property name or a script to evaluate, but cannot specify both.</span></span> <span data-ttu-id="a7276-123">Weitere Informationen zum Verwenden von Auswahl Bedingungen finden Sie unter [Definieren von Bedingungen für die Anzeige von Daten](./defining-conditions-for-displaying-data.md).</span><span class="sxs-lookup"><span data-stu-id="a7276-123">For more information about how to use selection conditions, see [Defining Conditions for when Data is Displayed](./defining-conditions-for-displaying-data.md).</span></span>

<span data-ttu-id="a7276-124">Weitere Informationen zu anderen Komponenten einer breiten Ansicht finden Sie unter [Wide View](./creating-a-wide-view.md).</span><span class="sxs-lookup"><span data-stu-id="a7276-124">For more information about other components of a wide view, see [Wide View](./creating-a-wide-view.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="a7276-125">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="a7276-125">See Also</span></span>

[<span data-ttu-id="a7276-126">Erstellen einer breiten Ansicht</span><span class="sxs-lookup"><span data-stu-id="a7276-126">Creating a Wide View</span></span>](./creating-a-wide-view.md)

[<span data-ttu-id="a7276-127">Definieren von Bedingungen für die Anzeige von Daten</span><span class="sxs-lookup"><span data-stu-id="a7276-127">Defining Conditions for When Data Is Displayed</span></span>](./defining-conditions-for-displaying-data.md)

[<span data-ttu-id="a7276-128">ScriptBlock-Element für selectioncondition für entryselectedby für wideentry (Format)</span><span class="sxs-lookup"><span data-stu-id="a7276-128">ScriptBlock Element for SelectionCondition for EntrySelectedBy for WideEntry (Format)</span></span>](./scriptblock-element-for-selectioncondition-for-entryselectedby-for-widecontrol-format.md)

[<span data-ttu-id="a7276-129">Selectioncondition-Element für entryselectedby für wideentry (Format)</span><span class="sxs-lookup"><span data-stu-id="a7276-129">SelectionCondition Element for EntrySelectedBy for WideEntry (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-widecontrol-format.md)

[<span data-ttu-id="a7276-130">Schreiben einer PowerShell-Formatierungsdatei</span><span class="sxs-lookup"><span data-stu-id="a7276-130">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
