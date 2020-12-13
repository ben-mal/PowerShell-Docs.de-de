---
ms.date: 09/13/2016
ms.topic: reference
title: Element „PropertyName“ für SelectionCondition für EntrySelectedBy für EnumerableExpansion (Format)
description: Element „PropertyName“ für SelectionCondition für EntrySelectedBy für EnumerableExpansion (Format)
ms.openlocfilehash: 8e28118894661b50e90a5ccc86a36fbbe77e4b03
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92665837"
---
# <a name="propertyname-element-for-selectioncondition-for-entryselectedby-for-enumerableexpansion-format"></a><span data-ttu-id="c125f-103">Element „PropertyName“ für SelectionCondition für EntrySelectedBy für EnumerableExpansion (Format)</span><span class="sxs-lookup"><span data-stu-id="c125f-103">PropertyName Element for SelectionCondition for EntrySelectedBy for EnumerableExpansion (Format)</span></span>

<span data-ttu-id="c125f-104">Gibt die .net-Eigenschaft an, die die Bedingung auslöst.</span><span class="sxs-lookup"><span data-stu-id="c125f-104">Specifies the .NET property that triggers the condition.</span></span> <span data-ttu-id="c125f-105">Wenn diese Eigenschaft vorhanden ist oder als ausgewertet wird `true` , wird die Bedingung erfüllt, und die Definition wird verwendet.</span><span class="sxs-lookup"><span data-stu-id="c125f-105">When this property is present or when it evaluates to `true`, the condition is met, and the definition is used.</span></span>

<span data-ttu-id="c125f-106">Configuration-Element (Format) DefaultSettings-Element (Format) enumerableweiterung-Element (Format) enumerableweiterung-Element (Format) entryselectedby-Element für enumerableexpansion (Format) selectioncondition-Element für entryselectedby für enumerableweiterung (Format) propertyName-Element für selectioncondition für entryselectedby für enumerableexpansion (Format)</span><span class="sxs-lookup"><span data-stu-id="c125f-106">Configuration Element (Format) DefaultSettings Element (Format) EnumerableExpansions Element (Format) EnumerableExpansion Element (Format) EntrySelectedBy Element for EnumerableExpansion (Format) SelectionCondition Element for EntrySelectedBy for EnumerableExpansion (Format) PropertyName Element for SelectionCondition for EntrySelectedBy for EnumerableExpansion (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="c125f-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="c125f-107">Syntax</span></span>

```xml
<PropertyName>.NetTypeProperty</PropertyName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="c125f-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="c125f-108">Attributes and Elements</span></span>

<span data-ttu-id="c125f-109">In den folgenden Abschnitten werden Attribute, untergeordnete Elemente und das übergeordnete Element des- `PropertyName` Elements beschrieben.</span><span class="sxs-lookup"><span data-stu-id="c125f-109">The following sections describe attributes, child elements, and the parent element of the `PropertyName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="c125f-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="c125f-110">Attributes</span></span>

<span data-ttu-id="c125f-111">Keine</span><span class="sxs-lookup"><span data-stu-id="c125f-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="c125f-112">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="c125f-112">Child Elements</span></span>

<span data-ttu-id="c125f-113">Keine</span><span class="sxs-lookup"><span data-stu-id="c125f-113">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="c125f-114">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="c125f-114">Parent Elements</span></span>

|<span data-ttu-id="c125f-115">Element</span><span class="sxs-lookup"><span data-stu-id="c125f-115">Element</span></span>|<span data-ttu-id="c125f-116">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c125f-116">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="c125f-117">Element „SelectionCondition“ für EntrySelectedBy für EnumerableExpansion (Format)</span><span class="sxs-lookup"><span data-stu-id="c125f-117">SelectionCondition Element for EntrySelectedBy for EnumerableExpansion (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-enumerableexpansion-format.md)|<span data-ttu-id="c125f-118">Definiert die Bedingung, die vorhanden sein muss, um die Auflistungs Objekte dieser Definition zu erweitern.</span><span class="sxs-lookup"><span data-stu-id="c125f-118">Defines the condition that must exist to expand the collection objects of this definition.</span></span>|

## <a name="text-value"></a><span data-ttu-id="c125f-119">Textwert</span><span class="sxs-lookup"><span data-stu-id="c125f-119">Text Value</span></span>

<span data-ttu-id="c125f-120">Geben Sie den Namen der .net-Eigenschaft an.</span><span class="sxs-lookup"><span data-stu-id="c125f-120">Specify the .NET property name.</span></span>

## <a name="remarks"></a><span data-ttu-id="c125f-121">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="c125f-121">Remarks</span></span>

<span data-ttu-id="c125f-122">Die Auswahlbedingung muss mindestens einen Eigenschaften Namen oder ein auszuwertende Skript angeben, kann jedoch nicht beides angeben.</span><span class="sxs-lookup"><span data-stu-id="c125f-122">The selection condition must specify at least one property name or a script to evaluate, but cannot specify both.</span></span> <span data-ttu-id="c125f-123">Weitere Informationen zum Verwenden von Auswahl Bedingungen finden Sie unter [Definieren von Bedingungen für die Anzeige von Daten](./defining-conditions-for-displaying-data.md).</span><span class="sxs-lookup"><span data-stu-id="c125f-123">For more information about how to use selection conditions, see [Defining Conditions for when Data is Displayed](./defining-conditions-for-displaying-data.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="c125f-124">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="c125f-124">See Also</span></span>

[<span data-ttu-id="c125f-125">Definieren von Bedingungen für die Anzeige von Daten</span><span class="sxs-lookup"><span data-stu-id="c125f-125">Defining Conditions for When Data is Displayed</span></span>](./defining-conditions-for-displaying-data.md)

[<span data-ttu-id="c125f-126">Element „ScriptBlock“ für SelectionCondition für EntrySelectedBy für EnumerableExpansion (Format)</span><span class="sxs-lookup"><span data-stu-id="c125f-126">ScriptBlock Element for SelectionCondition for EntrySelectedBy for EnumerableExpansion (Format)</span></span>](./scriptblock-element-for-selectioncondition-for-entryselectedby-for-enumerableexpansion-format.md)

[<span data-ttu-id="c125f-127">Element „SelectionCondition“ für EntrySelectedBy für EnumerableExpansion (Format)</span><span class="sxs-lookup"><span data-stu-id="c125f-127">SelectionCondition Element for EntrySelectedBy for EnumerableExpansion (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-enumerableexpansion-format.md)

[<span data-ttu-id="c125f-128">Schreiben einer PowerShell-Formatierungsdatei</span><span class="sxs-lookup"><span data-stu-id="c125f-128">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
