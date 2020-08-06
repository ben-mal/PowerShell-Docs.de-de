---
title: PropertyName-Element für selectioncondition für entryselectedby für enumerableweiterung (Format) | Microsoft-Dokumentation
ms.date: 09/13/2016
ms.openlocfilehash: c0081cb724ccaf1c04241aafa177880d7c0e5dbe
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2020
ms.locfileid: "87783465"
---
# <a name="propertyname-element-for-selectioncondition-for-entryselectedby-for-enumerableexpansion-format"></a><span data-ttu-id="49ce6-102">Element „PropertyName“ für SelectionCondition für EntrySelectedBy für EnumerableExpansion (Format)</span><span class="sxs-lookup"><span data-stu-id="49ce6-102">PropertyName Element for SelectionCondition for EntrySelectedBy for EnumerableExpansion (Format)</span></span>

<span data-ttu-id="49ce6-103">Gibt die .net-Eigenschaft an, die die Bedingung auslöst.</span><span class="sxs-lookup"><span data-stu-id="49ce6-103">Specifies the .NET property that triggers the condition.</span></span> <span data-ttu-id="49ce6-104">Wenn diese Eigenschaft vorhanden ist oder als ausgewertet wird `true` , wird die Bedingung erfüllt, und die Definition wird verwendet.</span><span class="sxs-lookup"><span data-stu-id="49ce6-104">When this property is present or when it evaluates to `true`, the condition is met, and the definition is used.</span></span>

<span data-ttu-id="49ce6-105">Configuration-Element (Format) DefaultSettings-Element (Format) enumerableweiterung-Element (Format) enumerableweiterung-Element (Format) entryselectedby-Element für enumerableexpansion (Format) selectioncondition-Element für entryselectedby für enumerableweiterung (Format) propertyName-Element für selectioncondition für entryselectedby für enumerableexpansion (Format)</span><span class="sxs-lookup"><span data-stu-id="49ce6-105">Configuration Element (Format) DefaultSettings Element (Format) EnumerableExpansions Element (Format) EnumerableExpansion Element (Format) EntrySelectedBy Element for EnumerableExpansion (Format) SelectionCondition Element for EntrySelectedBy for EnumerableExpansion (Format) PropertyName Element for SelectionCondition for EntrySelectedBy for EnumerableExpansion (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="49ce6-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="49ce6-106">Syntax</span></span>

```xml
<PropertyName>.NetTypeProperty</PropertyName>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="49ce6-107">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="49ce6-107">Attributes and Elements</span></span>

<span data-ttu-id="49ce6-108">In den folgenden Abschnitten werden Attribute, untergeordnete Elemente und das übergeordnete Element des- `PropertyName` Elements beschrieben.</span><span class="sxs-lookup"><span data-stu-id="49ce6-108">The following sections describe attributes, child elements, and the parent element of the `PropertyName` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="49ce6-109">Attribute</span><span class="sxs-lookup"><span data-stu-id="49ce6-109">Attributes</span></span>

<span data-ttu-id="49ce6-110">Keine</span><span class="sxs-lookup"><span data-stu-id="49ce6-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="49ce6-111">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="49ce6-111">Child Elements</span></span>

<span data-ttu-id="49ce6-112">Keine</span><span class="sxs-lookup"><span data-stu-id="49ce6-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="49ce6-113">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="49ce6-113">Parent Elements</span></span>

|<span data-ttu-id="49ce6-114">Element</span><span class="sxs-lookup"><span data-stu-id="49ce6-114">Element</span></span>|<span data-ttu-id="49ce6-115">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="49ce6-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="49ce6-116">Element „SelectionCondition“ für EntrySelectedBy für EnumerableExpansion (Format)</span><span class="sxs-lookup"><span data-stu-id="49ce6-116">SelectionCondition Element for EntrySelectedBy for EnumerableExpansion (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-enumerableexpansion-format.md)|<span data-ttu-id="49ce6-117">Definiert die Bedingung, die vorhanden sein muss, um die Auflistungs Objekte dieser Definition zu erweitern.</span><span class="sxs-lookup"><span data-stu-id="49ce6-117">Defines the condition that must exist to expand the collection objects of this definition.</span></span>|

## <a name="text-value"></a><span data-ttu-id="49ce6-118">Textwert</span><span class="sxs-lookup"><span data-stu-id="49ce6-118">Text Value</span></span>

<span data-ttu-id="49ce6-119">Geben Sie den Namen der .net-Eigenschaft an.</span><span class="sxs-lookup"><span data-stu-id="49ce6-119">Specify the .NET property name.</span></span>

## <a name="remarks"></a><span data-ttu-id="49ce6-120">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="49ce6-120">Remarks</span></span>

<span data-ttu-id="49ce6-121">Die Auswahlbedingung muss mindestens einen Eigenschaften Namen oder ein auszuwertende Skript angeben, kann jedoch nicht beides angeben.</span><span class="sxs-lookup"><span data-stu-id="49ce6-121">The selection condition must specify at least one property name or a script to evaluate, but cannot specify both.</span></span> <span data-ttu-id="49ce6-122">Weitere Informationen zum Verwenden von Auswahl Bedingungen finden Sie unter [Definieren von Bedingungen für die Anzeige von Daten](./defining-conditions-for-displaying-data.md).</span><span class="sxs-lookup"><span data-stu-id="49ce6-122">For more information about how to use selection conditions, see [Defining Conditions for when Data is Displayed](./defining-conditions-for-displaying-data.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="49ce6-123">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="49ce6-123">See Also</span></span>

[<span data-ttu-id="49ce6-124">Definieren von Bedingungen für die Anzeige von Daten</span><span class="sxs-lookup"><span data-stu-id="49ce6-124">Defining Conditions for When Data is Displayed</span></span>](./defining-conditions-for-displaying-data.md)

[<span data-ttu-id="49ce6-125">Element „ScriptBlock“ für SelectionCondition für EntrySelectedBy für EnumerableExpansion (Format)</span><span class="sxs-lookup"><span data-stu-id="49ce6-125">ScriptBlock Element for SelectionCondition for EntrySelectedBy for EnumerableExpansion (Format)</span></span>](./scriptblock-element-for-selectioncondition-for-entryselectedby-for-enumerableexpansion-format.md)

[<span data-ttu-id="49ce6-126">Element „SelectionCondition“ für EntrySelectedBy für EnumerableExpansion (Format)</span><span class="sxs-lookup"><span data-stu-id="49ce6-126">SelectionCondition Element for EntrySelectedBy for EnumerableExpansion (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-enumerableexpansion-format.md)

[<span data-ttu-id="49ce6-127">Schreiben einer PowerShell-Formatierungsdatei</span><span class="sxs-lookup"><span data-stu-id="49ce6-127">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
