---
ms.date: 09/13/2016
ms.topic: reference
title: Element „PropertyName“ für SelectionCondition für CustomControl für View (Format)
description: Element „PropertyName“ für SelectionCondition für CustomControl für View (Format)
ms.openlocfilehash: 1dd325a58b29a0f13b1341559c2a7dfe251c6b36
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92665854"
---
# <a name="propertyname-element-for-selectioncondition-for-customcontrol-for-view-format"></a><span data-ttu-id="e0f47-103">Element „PropertyName“ für SelectionCondition für CustomControl für View (Format)</span><span class="sxs-lookup"><span data-stu-id="e0f47-103">PropertyName Element for SelectionCondition for CustomControl for View (Format)</span></span>

<span data-ttu-id="e0f47-104">Gibt die .net-Eigenschaft an, die die Bedingung auslöst.</span><span class="sxs-lookup"><span data-stu-id="e0f47-104">Specifies the .NET property that triggers the condition.</span></span> <span data-ttu-id="e0f47-105">Wenn diese Eigenschaft vorhanden ist oder als ausgewertet wird `true` , wird die Bedingung erfüllt, und die Definition wird verwendet.</span><span class="sxs-lookup"><span data-stu-id="e0f47-105">When this property is present or when it evaluates to `true`, the condition is met, and the definition is used.</span></span> <span data-ttu-id="e0f47-106">Dieses Element wird beim Definieren einer benutzerdefinierten Steuerelement Ansicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="e0f47-106">This element is used when defining a custom control view.</span></span>

<span data-ttu-id="e0f47-107">Konfigurationselement (Format) viewdefinitions-Element (Format) View-Element (Format) CustomControl-Element für View (Format) customentries-Element für CustomControl for View (Format) customentry-Element für customentries für CustomControl for View (Format) customItem-Element für customentry für CustomControl for View (Format) entryselectedby-Element für customentry für CustomControl for View (Format) selectioncondition-Element für entryselectedby für CustomControl for View (Format) propertyName-Element für selectioncondition für CustomControl for View (Format)</span><span class="sxs-lookup"><span data-stu-id="e0f47-107">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) CustomControl Element for View (Format) CustomEntries Element for CustomControl for View (Format) CustomEntry Element for CustomEntries for CustomControl for View (Format) CustomItem Element for CustomEntry for CustomControl for View (Format) EntrySelectedBy Element for CustomEntry for CustomControl for View (Format) SelectionCondition Element for EntrySelectedBy for CustomControl for View (Format) PropertyName Element for SelectionCondition for CustomControl for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="e0f47-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="e0f47-108">Syntax</span></span>

```xml
<PropertyName>.NetTypeProperty</PropertyName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="e0f47-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="e0f47-109">Attributes and Elements</span></span>

<span data-ttu-id="e0f47-110">In den folgenden Abschnitten werden Attribute, untergeordnete Elemente und das übergeordnete Element des- `PropertyName` Elements beschrieben.</span><span class="sxs-lookup"><span data-stu-id="e0f47-110">The following sections describe attributes, child elements, and the parent element of the `PropertyName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="e0f47-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="e0f47-111">Attributes</span></span>

<span data-ttu-id="e0f47-112">Keine</span><span class="sxs-lookup"><span data-stu-id="e0f47-112">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="e0f47-113">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="e0f47-113">Child Elements</span></span>

<span data-ttu-id="e0f47-114">Keine</span><span class="sxs-lookup"><span data-stu-id="e0f47-114">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="e0f47-115">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="e0f47-115">Parent Elements</span></span>

|<span data-ttu-id="e0f47-116">Element</span><span class="sxs-lookup"><span data-stu-id="e0f47-116">Element</span></span>|<span data-ttu-id="e0f47-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e0f47-117">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="e0f47-118">Selectioncondition-Element für entryselectedby für CustomControl für View (Format)</span><span class="sxs-lookup"><span data-stu-id="e0f47-118">SelectionCondition Element for EntrySelectedBy for CustomControl for View (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-customcontrol-format.md)|<span data-ttu-id="e0f47-119">Definiert eine Bedingung, die vorhanden sein muss, damit die Steuerelement Definition verwendet werden muss.</span><span class="sxs-lookup"><span data-stu-id="e0f47-119">Defines a condition that must exist for the control definition to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="e0f47-120">Textwert</span><span class="sxs-lookup"><span data-stu-id="e0f47-120">Text Value</span></span>

<span data-ttu-id="e0f47-121">Geben Sie den Namen der .net-Eigenschaft an.</span><span class="sxs-lookup"><span data-stu-id="e0f47-121">Specify the .NET property name.</span></span>

## <a name="remarks"></a><span data-ttu-id="e0f47-122">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="e0f47-122">Remarks</span></span>

<span data-ttu-id="e0f47-123">Die Auswahlbedingung muss mindestens einen Eigenschaften Namen oder ein Skript angeben, kann jedoch nicht beides angeben.</span><span class="sxs-lookup"><span data-stu-id="e0f47-123">The selection condition must specify a least one property name or a script, but cannot specify both.</span></span> <span data-ttu-id="e0f47-124">Weitere Informationen zur Verwendung von Auswahl Bedingungen finden Sie unter Definieren von [Bedingungen zum Anzeigen von Daten](./defining-conditions-for-displaying-data.md).</span><span class="sxs-lookup"><span data-stu-id="e0f47-124">For more information about how selection conditions can be used, see [Defining Conditions for Displaying Data](./defining-conditions-for-displaying-data.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="e0f47-125">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="e0f47-125">See Also</span></span>

[<span data-ttu-id="e0f47-126">Selectioncondition-Element für entryselectedby für CustomControl für View (Format)</span><span class="sxs-lookup"><span data-stu-id="e0f47-126">SelectionCondition Element for EntrySelectedBy for CustomControl for View (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-customcontrol-format.md)

[<span data-ttu-id="e0f47-127">Schreiben einer PowerShell-Formatierungsdatei</span><span class="sxs-lookup"><span data-stu-id="e0f47-127">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
