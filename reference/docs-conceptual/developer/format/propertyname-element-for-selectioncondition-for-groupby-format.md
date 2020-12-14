---
ms.date: 09/13/2016
ms.topic: reference
title: Element „PropertyName“ für SelectionCondition für GroupBy (Format)
description: Element „PropertyName“ für SelectionCondition für GroupBy (Format)
ms.openlocfilehash: b89fead6185c88ca03956dc265135833696b91d7
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92665667"
---
# <a name="propertyname-element-for-selectioncondition-for-groupby-format"></a><span data-ttu-id="54809-103">Element „PropertyName“ für SelectionCondition für GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="54809-103">PropertyName Element for SelectionCondition for GroupBy (Format)</span></span>

<span data-ttu-id="54809-104">Gibt die .net-Eigenschaft an, die die Bedingung auslöst.</span><span class="sxs-lookup"><span data-stu-id="54809-104">Specifies the .NET property that triggers the condition.</span></span> <span data-ttu-id="54809-105">Wenn diese Eigenschaft vorhanden ist oder als ausgewertet wird `true` , wird die Bedingung erfüllt, und die Definition wird verwendet.</span><span class="sxs-lookup"><span data-stu-id="54809-105">When this property is present or when it evaluates to `true`, the condition is met, and the definition is used.</span></span> <span data-ttu-id="54809-106">Dieses Element wird verwendet, wenn definiert wird, wie eine neue Gruppe von Objekten angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="54809-106">This element is used when defining how a new group of objects is displayed.</span></span>

<span data-ttu-id="54809-107">Configuration-Element (Format) viewdefinitions-Element (Format) Ansichts Element (Format) GroupBy-Element für View (Format) CustomControl-Element für GroupBy (Format) customentries-Element für CustomControl für GroupBy (Format) customentry-Element für CustomControl für GroupBy (Format) entryselectedby-Element für customentry für GroupBy (Format) selectioncondition-Element für entryselectedby für GroupBy (Format) propertyName-Element für selectioncondition für GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="54809-107">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) GroupBy Element for View (Format) CustomControl Element for GroupBy (Format) CustomEntries Element for CustomControl for GroupBy (Format) CustomEntry Element for CustomControl for GroupBy (Format) EntrySelectedBy Element for CustomEntry for GroupBy (Format) SelectionCondition Element for EntrySelectedBy for GroupBy (Format) PropertyName Element for SelectionCondition for GroupBy (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="54809-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="54809-108">Syntax</span></span>

```xml
<PropertyName>.NetTypeProperty</PropertyName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="54809-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="54809-109">Attributes and Elements</span></span>

<span data-ttu-id="54809-110">In den folgenden Abschnitten werden Attribute, untergeordnete Elemente und das übergeordnete Element des- `PropertyName` Elements beschrieben.</span><span class="sxs-lookup"><span data-stu-id="54809-110">The following sections describe attributes, child elements, and the parent element of the `PropertyName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="54809-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="54809-111">Attributes</span></span>

<span data-ttu-id="54809-112">Keine</span><span class="sxs-lookup"><span data-stu-id="54809-112">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="54809-113">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="54809-113">Child Elements</span></span>

<span data-ttu-id="54809-114">Keine</span><span class="sxs-lookup"><span data-stu-id="54809-114">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="54809-115">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="54809-115">Parent Elements</span></span>

|<span data-ttu-id="54809-116">Element</span><span class="sxs-lookup"><span data-stu-id="54809-116">Element</span></span>|<span data-ttu-id="54809-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="54809-117">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="54809-118">Element „SelectionCondition“ für EntrySelectedBy für GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="54809-118">SelectionCondition Element for EntrySelectedBy for GroupBy (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-groupby-format.md)|<span data-ttu-id="54809-119">Definiert eine Bedingung, die vorhanden sein muss, damit die Steuerelement Definition verwendet werden muss.</span><span class="sxs-lookup"><span data-stu-id="54809-119">Defines a condition that must exist for the control definition to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="54809-120">Textwert</span><span class="sxs-lookup"><span data-stu-id="54809-120">Text Value</span></span>

<span data-ttu-id="54809-121">Geben Sie den Namen der .net-Eigenschaft an.</span><span class="sxs-lookup"><span data-stu-id="54809-121">Specify the .NET property name.</span></span>

## <a name="remarks"></a><span data-ttu-id="54809-122">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="54809-122">Remarks</span></span>

<span data-ttu-id="54809-123">Die Auswahlbedingung muss mindestens einen Eigenschaften Namen oder ein Skript angeben, kann jedoch nicht beides angeben.</span><span class="sxs-lookup"><span data-stu-id="54809-123">The selection condition must specify a least one property name or a script, but cannot specify both.</span></span> <span data-ttu-id="54809-124">Weitere Informationen zur Verwendung von Auswahl Bedingungen finden Sie unter Definieren von [Bedingungen zum Anzeigen von Daten](./defining-conditions-for-displaying-data.md).</span><span class="sxs-lookup"><span data-stu-id="54809-124">For more information about how selection conditions can be used, see [Defining Conditions for Displaying Data](./defining-conditions-for-displaying-data.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="54809-125">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="54809-125">See Also</span></span>

[<span data-ttu-id="54809-126">Element „SelectionCondition“ für EntrySelectedBy für GroupBy (Format)</span><span class="sxs-lookup"><span data-stu-id="54809-126">SelectionCondition Element for EntrySelectedBy for GroupBy (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-groupby-format.md)

[<span data-ttu-id="54809-127">Schreiben einer PowerShell-Formatierungsdatei</span><span class="sxs-lookup"><span data-stu-id="54809-127">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
